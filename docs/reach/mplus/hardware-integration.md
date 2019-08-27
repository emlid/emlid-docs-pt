
Reach suporta vários acessórios através da porta USB OTG e interface UART nos conectores de JST-GH.

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
|       TX       |       RX       |
|       RX       |       TX       |
|       GND      |       GND      |

#### Rádio 3DR

<div style="text-align: center;"><img src="../img/reachm-plus/hardware-integration/3dr.png" style="width: 700px;"></div><br>


Rádio 3DR também pode ser conectado via USB.

#### Rádio RFD900

<div style="text-align: center;"><img src="../img/reachm-plus/hardware-integration/rfd.png" style="width: 700px;"></div><br>

!!! Atenção ""
    Lembre-se que o RFD pode consumir até 800ma em picos, certifique-se que sua fonte de alimentação pode fornecer energia suficiente tanto para o Reach e para o RFD900.

<br>
#### Conectando radio USB ou modem LTE

<div style="text-align: center;"><img src="../img/reachm-plus/hardware-integration/lte-modem.png" style="width: 700px;"></div><br>

Para conectar o rádio USB ou modem LTE para o Reach use cabo USB-OTG, fornecido com o pacote. Ligue o rádio a porta USB-F e ligue o cabo Micro-USB no Reach.
**Ao usar a porta USB no modo OTG o Reach deve ser [alimentado](power-supply.md) por uma das portas JST-GH**.

!!! note "Conectando modem LTE"
	Tenha certeza que o Reach M+ está no modo ponto de acesso e o modem LTE foi pré-configurado para se conectar a internet automaticamente após iniciar.
<br>
#### Conectando rádio LoRa

<div style="text-align: center;"><img src="../img/reachm-plus/hardware-integration/lora.png" style="width: 700px;"></div><br>

Para conectar o rádio LoRa ao Reach use o conector JST-GH de cima (porta S2).
