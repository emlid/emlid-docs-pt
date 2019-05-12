## Correção da base

Configuração da correção é necessária se você quiser ir além do posicionamento autônomo. Reach suporta os seguintes formatos de correção: RTCM2, RTCM3, OEM4, OEM3, UBX, SS2, HEMIS, SKYTRAQ, SP3. RTCM3 é o formato mais popular na indústria. Dados em qualquer um desses formatos podem ser recebidos via Serial, TCP, NTRIP, Bluetooth ou LoRa para Reach RS/RS+.

### Serial

<p style="text-align:center" ><img src="../img/reachview/correction_input/serial.png" style="width: 800px;" /></p>

Conexão de porta serial está disponível através de várias opções de conexão de hardware. Todos eles suportam as seguintes taxas de transmissão: 4800, 9600, 14400, 19200, 28800, 38400, 56000, 57600, 115200, 128000, 153600, 230400, 256000, 460800, 921600.

#### UART
Corresponde a UART TTL no módulo Reach ou a porta RS232 no conector extensível do Reach RS/RS+. Maneira comum para ligar o rádio ou outro dispositivo que ofereça a correção.

#### USB-to-PC
Quando conectado por USB a um PC Reach vai aparecer como vários dispositivos, um deles será uma porta serial. Você pode usar a porta serial para enviar correções para o PC.

#### USB OTG
Use um cabo micro-USB OTG para conectar acessórios a porta USB. Neste modo, apenas os dispositivos USB que emulam uma porta serial podem ser usados. Exemplo de placas populares que são suportadas: FT232, CP2102. Existem inúmeros dispositivos construídos sobre esses chips que irão fornecer-lhe uma porta TTL UART ou RS232. Esta é uma maneira fácil de conectar os modems de rádio também.

### NTRIP

<p style="text-align:center" ><img src="../img/reachview/correction_input/ntrip.png" style="width: 800px;" /></p>

NTRIP é a maneira padrão de indústria de transferir correções GNSS através da internet, com ReachView você pode usar qualquer serviço público ou seu próprio Caster privado. NTRIP não oferece suporte a comunicação ponto a ponto, por exemplo, você não pode usar isso para transferir correções de um Reach ao outro diretamente. Na terminologia NTRIP existem servidores, clientes e um caster. O servidor envia correção para um caster e clientes podem recebê-las, conectando-se a esse caster.

A fim de receber correção de um caster NTRIP, você precisa saber:

+ Endereço de IP ou nome de domínio do caster
+	Porta (Port)
+	Usuário (Username)
+	Senha (Password)
+	Mountpoint
+	Formato (geralmente RTCM3)


Ao se conectar a uma estação de referência que tem VRS ou recurso “Nearest”, que automaticamente fornece uma conexão à estação base mais próxima, é necessário enviar sua posição para o caster. Marque a opção "enviar mensagens NMEA GGA para o servidor" e depois Reach obtém solução única ele vai começar a enviá-lo para o caster.

### TCP

<p style="text-align:center" ><img src="../img/reachview/correction_input/tcp.png" style="width: 800px;" /></p>


Cenário típico para usar correção TCP é quando a base e rover estão na mesma rede. Observe que quando os dispositivos estão em redes diferentes você não pode enviar dados diretamente a menos que os endereços de IP públicos são conhecidos e roteadores são configurados para encaminhamento de porta. TCP também pode ser usado para enviar dados para ou receber de um servidor remoto com IP público.

TCP suporta duas funções:

#### Server  
Você precisa especificar a porta e depois os clientes poderão se conectar a este dispositivo através do endereço de IP. Muitos clientes podem se conectar ao mesmo servidor.

#### Client
Você precisa especificar o endereço IP do servidor e número da porta.

Se ReachView não permite definir um determinado número de porta isso significa que é reservado para uso interno.

### LoRa Radio

<p style="text-align:center" ><img src="../img/reachview/correction_input/Lora.png" style="width: 800px;" /></p>

**Reach RS/RS+** tem rádio LoRa interno que é usado para receber ou enviar correções. Para Reach M+ o rádio externo LoRa está disponível, ele pode ser conectado via porta USB ou S1/S2. O rádio funciona apenas em uma forma, ele também poderia ser configurado para enviar correções (na base) ou para recebê-las (no rover). Usando módulo LoRa é possível alcançar até 19km em linha de visão ou alguns km em áreas urbanas com apenas 20 dBm de potência. Se os ajustes de taxa de frequência e intervalo forem o mesmo, um número ilimitado de rovers podem receber correção da mesma base.

Frequência e o intervalo (Air Rate) devem ser iguais ao que foi configurado na base.

### Bluetooth

<p style="text-align:center" ><img src="../img/reachview/correction_input/Bluetooth.png" style="width: 800px;" /></p>

Você pode usar o Bluetooth para entrada de correção. Por exemplo, você pode usar seu telefone para passar correções NTRIP via Bluetooth para o Reach RS/RS+. Confira a [seção de Bluetooth](connectivity/#bluetooth) para aprender mais sobre como conectar seu dispositivo através de Bluetooth.

## Correção adicional
Será usado para efemérides precisas e correções de relógio. Ainda não implementado.

<p style="text-align:center" ><img src="../img/reachview/correction_input/additional.png" style="width: 800px;" /></p>
