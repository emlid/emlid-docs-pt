!!! tip ""
	Reach has been replaced with [Reach M+](https://emlid.com/reach). Documentation for Reach M+ can be found [here](https://docs.emlid.com/reachm-plus/).

Reach supports various accessories via it's built-in USB OTG port and UART interface on the DF13 connector

### Rádio

É possível conectar módulos de rádio do Reach a fim de obter correções ou enviar coordenadas calculadas.

A maioria das rádios hoje em dia usam UART ou USB como conexão.

#### Conectando radio UART

Nível de carga da porta UART no Reach é 3.3V mas os pinos suportam até 5V, então você pode usar rádios de 3.3V e 5V.

Rádio UART é acessível no Reach como um dispositivo serial com o nome de **ttyMFD2**.

Para se conectar a rádio UART ao Reach use a porta JST-GH (S1).

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

Please note that a bug in the **Reach image before v1.2** prevents the Rover module from booting while it`s receiving UART correction signals from the base module. Current fix is powering up base module after the rover module has booted (LED are blinking red/blue/white).

#### Rádio RFD900

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-rfd900-radio.png" style="width: 550px;"></div><br>

Connection diagram for RFD900 radio:

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-rfd900-radio-connection-map.png" style="width: 550px;"></div><br>

!!! Atenção ""
    Lembre-se que o RFD pode consumir até 800ma em picos, certifique-se que sua fonte de alimentação pode fornecer energia suficiente tanto para o Reach e para o RFD900.

#### Connecting USB radio

<div style="text-align: center;"><img src="../img/reach/hardware-integration/reach-usb-radio.png" style="width: 550px;"></div><br>

To connect USB radio to Reach use USB-OTG cable provided with the package.
Plug radio into USB-F port and plug Micro-USB end of the cable in Reach.
**When using USB port in OTG mode Reach has to be [powered](power-supply.md) over one of the DF13 ports**.
