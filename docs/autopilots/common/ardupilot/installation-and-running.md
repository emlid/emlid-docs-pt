## Visão global

Você pode executar o  ArduPilot no Raspberry Pi 3 ou 2 com o Navio. O código do piloto automático funciona diretamente no Raspberry Pi. Para que o ArduPilot funcione corretamente, use a distribuioção Raspbian configurada que fornecemos.  

## Versões atuais do veículo

Emlid Rasbian tem o ArduPilot pré-instalado. Inclui todos os veículos e baseia-se no ramo estável disponível. Atualmente estes são:

* ArduCopter: **3.6.5**
* ArduPlane: **3.9.5**
* ArduRover: **3.4.2**
* ArduSub: **3.5.3**

## Cumprimento

Uma vez que você acessar (ssh) o Raspberry Pi você será recebido com uma mensagem que se parece com isso:

```
                                                                
                #     #    #    #     # ### ####### 
                ##    #   # #   #     #  #  #     # 
                # #   #  #   #  #     #  #  #     # 
                #  #  # #     # #     #  #  #     # 
                #   # # #######  #   #   #  #     # 
                #    ## #     #   # #    #  #     # 
                #     # #     #    #    ### ####### 
                                                                
Passo 1: 
Escolha seu veículo e versão do ArduPilot usando o emlidtool
(Por favor, leia atentamente todas as opções e selecione uma apropriada para o Navio 2 ou o Navio+)
- sudo emlidtool ardupilot

Passo 2:
Defina seu IP do GCS 
        - sudo nano /etc/default/arducopter
        - sudo nano /etc/default/arduplane
        - sudo nano /etc/default/ardurover
Passo 3:
Recarregar configurações emitindo esses comandos
        - sudo systemctl daemon-reload

Inicie e ative na inicialização

- sudo emlidtool ardupilot

IMPORTANTE:

Para mostrar esta mensagem mais uma vez digite "sudo emlidtool ardupilot help"

* Documentação: https://docs.emlid.com/
```

Nós vamos guiá-lo através do que está acontecendo sob o capô nas seções abaixo.

## Systemd

Para lançar o ArduPilot, estamos usando o sistema init `systemd`, que fornece o gerenciador para todos os serviçoes e processos. 
O comando principal usado para controlar o  systemd é `systemctl`. Alguns de seus usos são:

* examinando o estado do sistema 
* gerenciar o sistema e os serviçoes. 

Veja `man systemctl` para mais detalhes.

## Escolhendo um veículo, versão e placa

Para selecionar o veículo que seria lançado por padrão. você deve configurá-lo com o emlidtool:
```bash
sudo emlidtool ardupilot
```

Antes da configuração, o emlidtool verifica seu [RCIO](https://docs.emlid.com/navio2/dev/rcio) firmware and will suggest to update it if you have the outdated one:

!!! note ""
    Apenas para Navio2

![emlidtool-ui](img/emlidtool-rcio-update-dialog.png)

No exemplo abaixo, vamos usar o arducopter, mas poderia ter sido bem arduplane oo ardurover.
Quando o comando estiver em execução, ele produzirá a saída assim:

![emlidtool-ui](img/emlidtool.png)

Neste ponto, você deve inserir as opções corretas no menu à esquerda correspondente ao seu veículo e frame.
Além disso, você precisa decidir se deseja ativar o ardupilot no inicialização ou não e iniciá-lo/interrompê-lo agora.
  
Vamos supor que temos o arducopter e decidimos ativá-lo na inicialização e no início.

Depois de clicar no botão 'Apply', o ArduPilot será configurado e você verá as mudanças no widget ArdupilotInfo:

![emlidtool-ui](img/emlidtool-after-configure.png)

## Especificando opções de inicialização
 
Abra o arquivo:

```bash
pi@navio: ~ $ sudo nano /etc/default/arducopter 
```

Aqui você pode especificar o IP da sua estação.

```bash
TELEM1="-A udp:127.0.0.1:14550"
#TELEM2="-C /dev/ttyAMA0"

# Opções para passar para o ArduPilot
ARDUPILOT_OPTS="$TELEM1 $TELEM2"

# -A é um comutador de console (geralmente esse é um link de Wi-Fi)

# -C é um comutador de telemetria
# Normalmente, isso é /dev/ttyAMA0 - conector UART no seu Navio
# or /dev/ttyUSB0 se você estiver usando um serial para o conversor USB

# -B ou -E é usado para especificar o GPS não padrão
```

Todas as linhas marcadas com '#' são comentários e não têm efeito. 

Por exemplo, você precisará modificar o TELEM1 para apontar para o seu IP desta forma:

`TELEM1`="-A udp:192.168.1.2:14550"

Onde 192.168.1.2 é o endereço IP do dispositivo com a estação de controle no solo - seu laptop, smartphone, etc.

!!! tip ""
    Você pode adicionar opções adicionais ao `ARDUPILOT_OPTS` que são então passadas para o ArduPilot adicionando novas variáveis de ambiente `TELEM` como: `TELEM3`="-E /dev/ttyUSB1" `ARDUPILOT_OPTS`="$TELEM1 $TELEM2 $TELEM3"

Mapeamento entre comutadores e portas seriais (TCP ou UDP podem ser usados em vez de portas seriais):

* -A - serial 0 (sempre console; taca de transmissão padrão 115200)  
* -C - serial 1 (normalmente telemetria 1; taxa de transmissão padrão 57600)  
<sub>Rádios 3DR são configurados para 57600 por padrão, então a maneira mais simples de se conectar a eles é executar com a opção -C .</sub>
* -D - serial 2 (normalmente telemetria 2; taxa de transmissão padrão 57600)  
* -B - serial 3 (normalmente 1st GPS; taxa de transmissão padrão 38400)  
* -E - serial 4 (normalmente 2st GPS; taxa de transmissão padrão 38400)
* -F - serial 5  

Além disso, dê uma olhada na [lista de parâmetros de seriais](http://ardupilot.org/copter/docs/parameters.html?highlight=serial#serial-parameters) para o Mission Planner.

Ao usar a UART para telemetria, lembre-se de que as portas seriais têm taxas de transmissão padrão.   


## Recarregar configuração

Se você alterou alguma coisa na etapa anterior, precisará recarregar a configuração para que o systemd funcione corretamente.

```bash
pi@navio: ~ $ sudo systemctl daemon-reload
```

## Iniciando

Agora você pode iniciar o ArduPilot:

```bash
pi@navio: ~ $ sudo systemctl start arducopter
```

Para parar a execução do serviço:

```bash
pi@navio: ~ $ sudo systemctl stop arducopter
```

## Autoinicialização no boot

Para iniciar automaticamente o ArduPilot na inicialização, você precisa ativar o `arducopter`:

```bash
pi@navio: ~ $ sudo systemctl enable arducopter
```

Para desativar o início automático:
```bash
pi@navio: ~ $ sudo systemctl disable arducopter
```

Você pode verificar se o ArduPilot já está ativado ou não:
```bash
pi@navio: ~ $ systemctl is-enabled arducopter
```


## Conectando-se ao GCS

### Mission Planner

A Windows only ground station. É o recurso mais completo, no entendo.
Pode ser baixado no [ardupilot.com](http://firmware.ardupilot.org/Tools/MissionPlanner/)

### QGroundControl

A crossplatform ground station for Mavlink-based flight stacks (like Ardupilot).
Pode ser baixado no site [qgroundcontrol.com](https://docs.qgroundcontrol.com/en/getting_started/download_and_install.html)

### APM Planner

APM Planner is a ground station software for ArduPilot. Pode ser baixado no [ardupilot.com](http://firmware.ardupilot.org/Tools/APMPlanner/)

O APM Planner capta na porta UDP 14550, por isso deve capturar a telemetria do drone automaticamente.
Além disso, se você estiver usando o Linux, você deve adicionar seu usuário ao grupo de discagem:
 
```bash
sudo adduser $USER dialout
```

### MAVProxy

MAVProxy is a console-oriented ground station software written in Python. It’s well suited for advanced users and developers.

Para instalar o MAVProxy use [Download E Instalação](http://ardupilot.github.io/MAVProxy/html/getting_started/download_and_installation.html) instructions.


Para executá-lo, especifique a --master port, que pode ser serial, TCP ou UDP. Também pode executar passagem de dados usando a opção --out.

```bash
pi@navio: ~ $ mavproxy.py --master 192.168.1.2:14550 --console
```

Onde 192.168.1.2 é o endereço IP do GCS, não o RPi.

## Iniciando um binário personalizado do ArduPilot

O Navio é suportado no ArduPilot upstream e, se você quiser construir o binário, por favor, vá para o [Construindo a partir de fontes](building-from-sources.md). Além disso, você pode fazer o download dos arquivos binários mais recentes do ArduPilot buildserver. Para baixar o binário arducopter:

```bash
pi@navio: ~ $ wget http://firmware.eu.ardupilot.org/Copter/stable/navio2/arducopter
pi@navio: ~ $ chmod +x arducopter
```
Em caso de uso de helicopter, mude a cauda do link.  Por exemplo, `/navio2-heli/arducopter-heli`. Os tipos de veículos suportados estão listados abaixo:

* ArduRover
* ArduPlane
* ArduCopter
* ArduCopter-heli

Se você deseja iniciar um binário personalizado, é esperado que você modifique e use /etc/systemd/system/ardupilot.service

```bash

[Unit]
Description=ArduPilot for Linux
After=systemd-modules-load.service
Documentation=https://docs.emlid.com/navio2/navio-ardupilot/installation-and-running/#autostarting-ardupilot-on-boot
Conflicts=arduplane.service arducopter.service ardurover.service

[Service]
EnvironmentFile=/etc/default/ardupilot

###################################################################################### ### NÃO EDITAR ACIMA DESTA LINHA, A AMENOS QUE VOCÊ SAIBA O QUE VOCÊ ESTÁ FAZENDO ####
######################################################################################

# Descomente e modifique esta linha de você quiser lançar seu próprio binário
#ExecStart=/bin/sh -c "/home/pi/<path>/<to>/<your>/<binary> ${ARDUPILOT_OPTS}"

##### CAUTION ######
# Deve haver apenas um ExecStart não comentado neste arquivo

######################################################################################### NÃO EDITAR ABAIXO DESTA LINHA, A MENOS QUE VOCÊ SAIBA O QUE VOCÊ ESTÁ FAZENDO #### ######################################################################################

Restart=on-failure

[Install]
WantedBy=multi-user.target
```

Os comentários falam por si. A única coisa que você presica ajustar é 
```bash
#ExecStart=/bin/sh -c "/home/pi/<path>/<to>/<your>/<binary> ${ARDUPILOT_OPTS}"
```
para algo assim
```bash
ExecStart=/bin/sh -c "/home/pi/arducopter-quad ${ARDUPILOT_OPTS}"
```
Além disso, o procedimento de inicialização não é diferente do descrito acima, com a única exceção que você presica usar o utilitário systemctl com o serviço `arducopter`/`arduplane`/`ardurover` e usar `/etc/default/ardupilot` para modificações de `ARDUPILOT_OPTS`.

O comando abaixo irá iniciar o binário do ArduPilot personalizado e depois marcá-lo para iniciar na inicialização:

```bash
pi@navio: ~ sudo systemctl start ardupilot && sudo systemctl enable ardupilot
```
