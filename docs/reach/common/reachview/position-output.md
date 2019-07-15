
### Formatos

<p style="text-align:center" ><img src="../img/reachview/position_output/format.png" style="width: 800px;" /></p>

Reach suporta enviar os seguintes formatos de posição:

#### LLH
Protocolo de texto simples para Latitude Longitude e altura bem como status de solução. Definição de protocolo pode ser encontrada no [Manual do RTKLIB versão 2.4.2](http://www.rtklib.com/prog/manual_2.4.2.pdf) na página 102.

#### XYZ
Protocolo de texto simples para coordenadas ECEF, formato X, Y, Z bem como status de solução. Definição de protocolo pode ser encontrada no [Manual do RTKLIB versão 2.4.2](http://www.rtklib.com/prog/manual_2.4.2.pdf) na página 102.

#### ENU
Protocolo de texto simples para componentes de Leste, Norte e Altura da linha de base bem como status de solução. Definição de protocolo pode ser encontrada no [Manual do RTKLIB versão 2.4.2](http://www.rtklib.com/prog/manual_2.4.2.pdf) na página 102.

#### NMEA 0183
O padrão mais popular da indústria. Suporta mensagens: GNRMC, GNGGA, GPGSA, GLGSA, GAGSA, GPGSV, GLGSV, GAGSV, GNGST, GNVTG.

Definição de protocolo pode ser encontrada no [Manual do RTKLIB versão 2.4.2](http://www.rtklib.com/prog/manual_2.4.2.pdf) na página 102.

#### ERB
Usado para comunicação com o Ardupilot, a descrição do protocolo pode ser encontrada [aqui](https://files.emlid.com/ERB.pdf).


**Dados em qualquer um destes formatos podem ser enviados via Serial, TCP ou Bluetooth.**

### Serial
Conexão de porta serial está disponível através de várias opções de conexão de hardware. Todos eles suportam as seguintes taxas comunicação: 4800, 9600, 14400, 19200, 28800, 38400, 56000, 57600, 115200, 128000, 153600, 230400, 256000, 460800.

#### UART
Corresponde a módulo UART TTL no Reach ou a porta RS232 ou conector de extensão no Reach RS/RS+. Maneira comum para se conectar ao piloto automático ou outro consumidor de dados de posição.

#### USB-to-PC
Quando conectado por USB a um PC Reach vai aparecer como vários dispositivos, um deles será uma porta serial. Você pode usar a porta serial para enviar dados de posição para o PC.

#### USB OTG
Use um cabo micro-USB OTG para conectar acessórios a porta USB. Neste modo, apenas os dispositivos USB que emulam uma porta serial podem ser usados. Exemplo de placas populares que são suportadas: FT232, CP2102. Existem inúmeros dispositivos construídos sobre esses chips que irão fornecer-lhe uma porta TTL UART ou RS232.

### TCP
Cenário típico para usar TCP é o envio dados de posição para uma aplicação na mesma rede ou a um servidor com IP público..

TCP suporta duas funções:

#### Server
Você precisa especificar a porta e depois os clientes poderão se conectar a este dispositivo através do endereço de IP. Muitos clientes podem se conectar ao mesmo servidor.

#### Client
Você precisa especificar o endereço IP do servidor e número da porta.

Se ReachView não permite definir um determinado número de porta isso significa que é reservado para uso interno.

### Bluetooth
Saída de Bluetooth é usada para transmitir dados de posição para smartphones, tablets ou coletores de dados. Por favor, certifique-se de emparelhar o seu dispositivo em configurações de Bluetooth.

!!! note ""
	Dispositivos iOS não suportam obter posição através do Bluetooth usando hardware de terceiros.
