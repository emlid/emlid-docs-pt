## Corrections output

<p style="text-align:center"><img src="../img/reachview/base_mode/output.png" style="width: 800px;"/></p>

Reach envia correção em formato de RTCM3 padrão da indústria. Dados corrigidos podem ser enviados via Serial, TCP, NTRIP ou LoRa para Reach RS/RS+.

### Serial
Conexão de porta serial está disponível através de várias opções de conexão de hardware. Todos eles suportam as seguintes taxas de transmissão: 4800, 9600, 14400, 19200, 28800, 38400, 56000, 57600, 115200, 128000, 153600, 230400, 256000, 460800.

#### UART
Corresponde a UART TTL no módulo Reach ou a porta RS232 no conector extensível do Reach RS/RS+. Maneira comum para ligar o rádio ou outro dispositivo que ofereça a correção.

#### USB-to-PC
Quando conectado por USB a um PC Reach vai aparecer como vários dispositivos, um deles será uma porta serial. Você pode usar a porta serial para enviar correções para o PC.

#### USB OTG
Use um cabo micro-USB OTG para conectar acessórios a porta USB. Neste modo, apenas os dispositivos USB que emulam uma porta serial podem ser usados. Exemplo de placas populares que são suportadas: FT232, CP2102. Existem inúmeros dispositivos construídos sobre esses chips que irão fornecer-lhe uma porta TTL UART ou RS232.

### NTRIP
NTRIP é a maneira padrão de indústria de transferir correções GNSS através da internet, com ReachView você pode usar qualquer serviço público ou seu próprio Caster privado. NTRIP não oferece suporte a comunicação ponto a ponto, por exemplo, você não pode usar isso para transferir correções de um Reach ao outro diretamente. Na terminologia NTRIP existem servidores, clientes e um caster. O servidor envia correção para um caster e clientes podem recebê-las, conectando-se a esse caster.

A fim de receber correção de um caster NTRIP, você precisa saber:

-	Endereço de IP ou nome de domínio do caster
-	Porta (Port)
-	Usuário (Username)
-	Senha (Password)
-	Mountpoint
-	Formato (geralmente RTCM3)

Quando conectando via NTRIP em modo base o Reach atua como um servidor NTRIP.

### TCP
Cenário típico para usar TCP é o envio dados de posição para uma aplicação na mesma rede ou a um servidor com IP público.

TCP suporta duas funções:

#### Server
Você precisa especificar a porta e depois os clientes poderão se conectar a este dispositivo através do endereço de IP. Muitos clientes podem se conectar ao mesmo servidor.
#### Client
Você precisa especificar o endereço IP do servidor e número da porta.

Se ReachView não permite definir um determinado número de porta isso significa que é reservado para uso interno.


### LoRa Radio
**Reach RS/RS+** tem rádio LoRa interno que é usado para receber ou enviar correções. Para **Reach M+** o rádio externo LoRa está disponível, ele pode ser conectado via porta USB ou S1/S2. O rádio funciona apenas em uma forma, ele também poderia ser configurado para enviar correções (na base) ou para recebê-las (no rover). Usando módulo LoRa é possível alcançar até 19km em linha de visão ou alguns km em áreas urbanas com apenas 20 dBm de potência. Se os ajustes de taxa de frequência e intervalo forem o mesmo, um número ilimitado de rovers podem receber correção da mesma base.
Menor o intervalo, maior a distância de trabalho será. Dependendo do seu RTCM3 seleção de mensagens ReachView bloqueará automaticamente intervalos insuficientes. Desative mensagens de correção para desbloquear intervalos mais baixos. Intervalos de transmissão e recepção do Reach devem corresponder.
Certifique-se de selecionar a potência de saída apropriada e a frequência de acordo com os regulamentos locais.

	!!! Dica ""
	No Brasil, a frequência de operação do rádio LoRa é reservada para uso civil, portanto não há necessidade de homologação.

### Bluetooth
Você pode usar o Bluetooth para entrada de correção. Observe que você não pode definir tanto a saída de posição e envio de correção da base via Bluetooth ao mesmo tempo.

## Mensagens RTCM3

<p style="text-align:center"><img src="../img/reachview/base_mode/messages.png" style="width: 800px;"/></p>
O conjunto mínimo que é exigido para função RTK é a mensagem 1002 para 1Hz com observações GPS e mensagem 1006 para 0,1 Hz com posição de antena da estação base. Habilitar mais mensagens ou taxas mais elevadas exige maior conexão de banda.

Na linha de taxa de dados você pode encontrar uma estimativa de bytes/s quando as mensagens são configuradas em 1 Hz.

|Mensagens RTCM3|Tipo de mensagem|Taxa de dados, bytes/s (1 satélite, 1Hz)|
|:---:|:---:|:---:|
||**Mensagens mecessárias**||
|1002|Observações GPS L1|10.39|
|1006|Coordenada ARP da estação| 27|
||**Mensagens opcionais para outros GNSS**||
|1010|Observações GLONASS L1|11.3|
|1097|GALILEO MSM|21.5|
|1107|SBAS MSM|37.5|
|1117|QZSS MSM|42|
|1127|BeiDou MSM|17.78|


Aqui estão algumas informações sobre cada mensagem RTCM padrão 10403.31[1](#myfootnote1)</sup>:

- **Mensagem 1002 e 1010** contém L1 RTK GPS e dados do satélite GLONASS, respectivamente. Mensagem de GPS 1002 é obrigatória usar devido ao código de RTKLIB. Você poderia ligar a mensagem 1010 GLONASS se você quiser usar esta constelação GNSS.

- **Mensagem 1006** fornece as coordenadas (ECEF) do ponto de referência da antena (ARP) para uma estação de referência e a altura do ARP do levantamento. É a segunda mensagem obrigatória para ligar depois de GPS 1002.

- **Mensagem 1097 (GALILEO), 1107 (SBAS), 1117 (QZSS), 1127 (BeiDou)** são MSM7 (Multiple Signal Messages). MSM7 são mensagens de alta precisão que contém um conjunto completo de observações RINEX. Isso significa que você deve ligar somente uma mensagem do sistema escolhido para obter todos os dados.

	!!! Dica ""
		Lembre-se, que você não pode usar sistemas GLONASS e BeiDou juntos.

	!!! Dica ""
		* Use a mensagem 1117 (QZSS) se você estiver localizado no sudeste asiático e Austrália.
		* Use a mensagem 1107 (SBAS) se você está localizado na America do Norte, Europa, Norte da África, Oriente Médio, sul da Ásia e sudeste Asiático, Rússia.
		* Use a mensagem 1127 (BeiDou) se você estiver localizado na região da Ásia e Austrália.


## Base position

<p style="text-align:center"><img src="../img/reachview/base_mode/position.jpg" style="width: 800px;"/></p>

Existem duas opções principais como especificar a posição da estação base. Observe que o posicionamento RTK é relativo a estação de base, então qualquer imprecisão em sua posição irá resultar em uma mudança constante nas coordenadas do rover. Para muitas aplicações não é crítica, e pode ser utilizada uma média de coordenadas autônomas da base. Se seu aplicativo requer precisão absoluta para posição de rover que uma coordenada base exata deve ser inserida.

### Manual
Neste modo você fornecer um a priori coordenada conhecida do ponto em que a base está instalada. Coordenada deve ser inserida no formato ECEF XYZ ou WGS84 Latitude e Longitude e altura elipsoidal do WGS84. A altura da antena também é inserida nesta etapa, esta altura é limitado a 6,5535m pela mensagem RTCM.

Você pode alterar o formato da posição no canto superior direito do quadro de coordenadas Base.

<p style="text-align:center"><img src="../img/reachview/base_mode/manual.jpg" style="width: 800px;"/></p>

### Average (Média)
Por padrão Reach utiliza uma média de leituras autônomas para iniciar a base. Esse recurso simplifica significativamente a configuração inicial em um novo local, porém não fornecerá uma coordenada absoluta precisa.

ReachView tem uma opção que permite determinar a posição da base, enquanto trabalhando como um rover de outra base. Isto é feito através da obtenção de solução RTK fixa, durante um período de tempo e assim obter uma posição exata para a base. Um cenário típico envolveria a criação de uma estação de base local com suas coordenadas determinadas via NTRIP e então transmitindo correção localmente, a partir de um ponto conhecido, reduzindo assim a linha de base para rovers melhorando o posicionamento e desempenho.

Se a estação de referência está muito longe... é possível inserir uma média de solução flutuante e ainda melhorar a precisão da posição.

Caso nenhuma correção esteja disponível ao configurar a base ou precisão absoluta não é necessária, a média de coordenadas navegadas podem ser usadas.


**Salvar posição média para manual**  
Após obtido uma média de posição, você pode querer guardar para uso futuro. Clique no ícone Save coordinates (Salvar coordenadas) e a posição será salva, como se ela fosse inserida no modo manual. Agora toda vez que o Reach iniciar, ele enviará correção a utilizando esta posição como referência.

**Repetir média**  
Se você deseja reiniciar a posição da base através de uma média, você pode clicar no ícone Repeat averaging (Repetir média). Isto é especialmente útil em uma situação em que você acidentalmente moveu o Reach durante a coleta da média.

<p style="font-size:70%;"><a name="myfootnote1">1</a>: Radio Technical Commission for Maritime Services. 2016. RTCM STANDARD 10403.3 DIFFERENTIAL GNSS (GLOBAL NAVIGATION SATELLITE SYSTEMS) SERVICES – VERSION 3. Virginia: Radio Technical Commission for Maritime Services, pp. 108-262</p>
