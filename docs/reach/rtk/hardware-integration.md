!!! tip ""
	Reach Module foi substituído por [Reach M+](https://emlid.com/reach). A documentação para o Reach M + pode ser encontrada [aqui](https://docs.emlid.com/reachm-plus/).

O Reach Module suporta vários acessórios através da porta USB OTG incorporada e interface UART no conector DF13.

### Rádio

É possível conectar módulos de rádio do Reach Module a fim de obter correções ou enviar coordenadas calculadas.

A maioria das rádios hoje em dia usam UART ou USB como conexão.

#### Conectando radio UART

Nível de carga da porta UART no Reach Module é 3.3V mas os pinos suportam até 5V, então você pode usar rádios de 3.3V e 5V.

Rádio UART é acessível no Reach Module como um dispositivo serial com o nome de **ttyMFD2**.

Para se conectar a rádio UART ao Reach Module use a porta JST-GH (S1).

| Pinos do Reach | Pinos do Rádio |
|:--------------:|:--------------:|
|      +5V       |      +5V       |
|      TX        |      RX        |
|      RX        |      TX        |
|      GND       |      GND       |

#### Rádio 3DR

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-3dr-radio.png" style="width: 550px;"></div><br>

Diagrama de conexão para 3DR Radio v2:

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-3dr-radio-connection-map.png" style="width: 550px;"></div><br>

Rádio 3DR também pode ser conectado via USB.

Observe que um bug na imagem do **Reach Module antes da v1.2** impede o módulo Rover de inicializar enquanto está `recebendo sinais de correção UART do módulo base. A correção atual está energizando o módulo base após inicializar o rover (o LED está piscando em vermelho/azul/branco).

#### Rádio RFD900

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-rfd900-radio.png" style="width: 550px;"></div><br>

Diagrama de conexão para o rádio RFD900:

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-rfd900-radio-connection-map.png" style="width: 550px;"></div><br>

!!! Atenção ""
    Lembre-se que o RFD pode consumir até 800ma em picos, certifique-se que sua fonte de alimentação pode fornecer energia suficiente tanto para o Reach e para o RFD900.

#### Conectando o rádio USB

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-usb-radio.png" style="width: 550px;"></div><br>

Para conectar o rádio USB ao Reach Module, use o cabo USB-OTG fornecido com o pacote. 
Conecte o rádio na porta USB-F e conecte a extremidade Micro-USB do cabo no Reach Module.
**Ao usar a porta USB no modo OTG, o Reach Module tem que ser [energizado](power-supply.md) sobre uma das portas DF13 ports**.
