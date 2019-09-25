## Correction output (Saída de correção)

<p style="text-align:center"><img src="../img/reachview/base-mode/output.png" style="width: 800px;"/></p>

O Reach utiliza como correction output o formato RTCM3, que é um formato padrão da indústria. Os dados de correção podem ser enviados via Serial, TCP, NTRIP ou LoRa.

### Serial
A conexão da porta serial está disponível através de várias opções de conexão de hardware. Todos eles suportam as seguintes taxas de trasnmissão: 4800, 9600, 14400, 19200, 28800, 38400, 56000, 57600, 115200, 128000, 153600, 230400, 256000, 460800.

#### UART
Corresponde à porta RS232 no conector de extensão do Reach RS2. Maneira comum de conectar ao rádio para enviar dados de correção.

#### USB-para-PC
Quando conectado via USB a um PC, o Reach será exibido como vários dispositivos, um deles será uma porta serial. Você pode usar esta porta serial para enviar dados de correção para o PC.

#### USB OTG
Use um cabo micro-USB OTG para conectar acessórios USB. Nesse modo, apenas os dispositivos USB que emulam uma porta serial podem ser usados. Exemplo de chips populares suportados:FT232, CP2102. Existem vários dispositivos criados nesses chips que fornecerão uma porta TTL UART ou RS232. 

### NTRIP
O NTRIP é a maneira padrão da indústria de transferir correções GNSS pela internet. Com o ReachView, você pode usar qualquer serviço público ou seu próprio caster. O NTRIP não suporta comunicação ponto a ponto, por exemplo você não pode usá-lo para transferir correções de um Reach para outro diretamente. Na terminologia NTRIP, existem servidores, clientes e casters. O servidor envia a correção para um caster e os clientes podem recebê-los conectando-se a esse caster.

Para enviar a correção para um caster NTRIP, você precisa saber: 

- IP adress ou nome de domínio do caster
- Port (Porta)
- Username (Usuário)
- Password (Senha)
- Mount point (Nome da base)

A o conectar via NTRIP na base mode (modo base), o Reach atua como um servidor NTRIP.

### TCP
O cenário típico para o uso do TCP é o envio de dados de correção para um aplicativo na mesma rede ou para um servidor com IP público.

O TCP suporta duas funções:

#### Server (Servidor)
Você precisa especificar a porta e, depois disso, os clientes poderão se conectar a este dispositivo no endereço IP. Muitos clientes podem estar conectados ao mesmo servidor.
#### Client (Cliente)
Você precisa especificar o endereço IP do servidor e o número da porta.

Se o ReachView não permitir definir um determinado número de porta, significa que ele está reservado para o uso interno.

### LoRa Radio (Rádio LoRa)
O Reach RS2 possui um rádio LoRa interno que é usado para receber ou enviar correções. O rádio funciona apenas de uma maneira: ele pode ser configurado para enviar correções (na base) ou recebê-las (no rover). Usando a modulação LoRa, é possível atingir até 8 km na linha de visão ou alguns km em áreas urbanas com apenas 20 dBm de potência. Contando que as configurações de frequência e air rate correspondam a um número ilimitado de rovers, é possível receber correção da mesma base.

Quanto menor a air rate, maior será a linha de base. Dependendo da sua seleção de mensagens do RTCM3, o ReachView bloqueará automaticamente as air rate insuficientes. Desative as mensagens de correção ou reduza a taxa para desbloquear as air rate mais baixas. A air rate na trasnmissão do Reach e na recepção devem corresponder.

Certifique-se de selecionar a potência e a frequência de saída apropriadas, de acordo com os regulamentos locais..

### Bluetooth
Você pode usar o Bluetooth para saída de correção. Observe que você não pode definir a saída de posição e a saída de correção básica para o Bluetooth ao mesmo tempo..

## RTCM3 messages (Mensagens RTCM3)

<p style="text-align:center"><img src="../img/reachview/base-mode/messages.png" style="width: 800px;"/></p>
As mínimas mensagens necessárias para o RTK funcionar são as mensagens 1074 em 1 Hz com as observações GPS e a 1006 em 0,1 Hz com a posição da antena da estação base. A ativação de mais mensagens ou taxas mais altas requer maior largura de banda de conexão.

Em Data rate (taxa de dados), você pode encontrar uma estimativa de bytes/s para 1 satélite quando as mensagens são configuradas em 1 Hz.

|Mensagens RTCM3|Tipo de mensagem|Taxa de dados, bytes/sec (1 satélite, 1Hz)|
|:---:|:---:|:---:|
||**Mensagens mínimas requeridas**||
|1006|ARP station coordinate   | 27|
|1074|GPS MSM4      |19.38|
||**Mensagens opcionais para outras constelações **||
|1084|GLONASS MSM4|19.38|
|1094|Galileo MSM4|9.58|
|1124|BeiDou MSM4|18.9|


Aqui estão algumas informações sobre acada mensagem do RTCM STANDARD 10403.3<sup>[1](#myfootnote1)</sup>:

- **Tipo de mensagem 1006** fornece as coordenadas (ECEF) do ponto de referência da antena (ARP) para uma estação de referência estacionária e a altura do ARP acima de um monumento de pesquisa. É uma mensagem obrigatória para ativar.

- **As mensagens 1074 (GPS), 1084(GLONASS), 1094 (Galileo), 1124 (BeiDou)** são MSM4 (Multiple Signal Messages - Mensagens de sinal múltiplo). Os MSM4 são mensagens de alta precisão que contêm um conjunto completo de observações RINEX com resolução estendida. Isso significa que você deve ativar apenas uma mensagem do sistema escolhido para obter todos os dados sobre ele. Recomenda-se manter ativada pelo menos a mensagem GPS 1074.

## Base position


!!! tip ""
    [Verifique o guia Montando a base](https://docs.emlid.com/reachrs2/common/tutorials/placing-the-base/) para aprender sobre diferentes maneiras de configurar sua base.

<p style="text-align:center"><img src="../img/reachview/base-mode/position.jpg" style="width: 800px;"/></p>

Existem duas opções principais como especificar a posição da estação base. Observe que o posicionamento RTK é relativo à estação base, portanto, qualquer imprecição na posição resultará em uma mudança constante de coordenadas no rover. Para muitas aplicações, isso não é crítico e a coordenada média average single pode ser usada. Se a sua aplicação requer precisão absoluta para a posição do rover, uma coordenada de base precisa deve ser inserida.

### Manual
Nesse modo, você fornece uma coordenada conhecida a priori, localizando a unidade acima do ponto pesquisado. A coordenada deve ser fornecida em ECEF XYZ ou em latitude, longiutde e altura elipsoidal WGS84. O deslocamente da altura da antena também é inserido neste estágio, o deslocamente é limitado a 6,5535 m pela mensagem RTCM.

Você pode alterar o formato da posição no canto superior direito do quadro de coordenadas  da base.

<p style="text-align:center"><img src="../img/reachview/base-mode/manual.jpg" style="width: 800px;"/></p>

### Average (Valor médio)
Por padrão, o Reach medirá a base position (posição da base) toda vez que é iniciado. Esse recurso simplifica significativamente a configuração inicial em um novo local, mas não fornece uma coordenada absoluta precisa.

O ReachView possui um recurso exclusivo que permite determinar a posição da estação base enquanto trabalha como rover de outra base. Isso é feito através da obtenção da solução RTK Fixed, calculando a média por um período de tempo e, dessa forma, obtendo uma posição precisa para a base. Um cenário típico envolveria a instalação de uma estação base local, determinando sua coordenada por NTRIP e transmitindo a correção localmente, reduzindo assim a linha de base para rovers e melhorando o desempenho do posicionamento.

Se a estação de referência estiver muito distante, é possível fazer average float e ainda melhorar a precisão da posição.

Caso nenhuma correção esteja disponível quando a configuração da base ou a precisão absoluta não forem necessárias, poderão ser usadas as coordenadas average single.

**Salve a posição média no modo manual**  
Depois de obter com êxito a posição média, convém salvá-la para uso futuro. Clique no ícone “save coordinates” e a posição será salva como se tivesse sido inserida no modo manual. Agora, toda vez que o Reach iniciar, ele transmitirá essa posição nas mensagens de correção.

**Repetir a média**  
Se você deseja reiniciar o processo de média da posição base, clique no ícone “repeat averaging”. Isso é especialmente útil em uma situação em que você acidentalemnte moveu o Reach durante a média.

<p style="font-size:70%;"><a name="myfootnote1">1</a>: Radio Technical Commission for Maritime Services. 2016. RTCM STANDARD 10403.3 DIFFERENTIAL GNSS (GLOBAL NAVIGATION SATELLITE SYSTEMS) SERVICES – VERSION 3. Virginia: Radio Technical Commission for Maritime Services, pp. 108-262</p>


