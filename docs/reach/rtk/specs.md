!!! tip ""
	O Reach Module foi substituído por [Reach M+](https://emlid.com/reach). A documentação do Reach M+ pode ser encontrada [aqui](https://docs.emlid.com/reachm-plus/).

## Especificações mecânicas

### Dimensões

O módulo Reach Module é um pequeno dispositivo, é apenas alguns milímetros maior do que o Intel Edinson que ele hospeda.

<div style="text-align: center;"><img src="../img/reach/specs/reach-dimensions.png" style="width: 350px;"></div><br>

### Partes dos conectores

O Reach Module tem dois conectores DF13 e vem com todos os cabos necessários para se conectar a outros dispositivos. Caso você queira fazer sua própria montagem de cabos, aqui estão os números de peça de conectores apropriados:

* No Reach Module: Hirose DF13-6P-1.25H(50) ([Digikey](http://www.digikey.com/product-detail/en/DF13-6P-1.25H%2850%29/H3354-ND/530653), [Mouser](http://eu.mouser.com/ProductDetail/Hirose-Electric/DF13-6P-125H50/?qs=%2fha2pyFaduilOJdMONLaLBwaFNH0V7VnzXasUV9hMRidfNFMCnSnIA%3d%3d)).

* Receptáculo: Hirose DF13-6S-1.25C ([Digikey](http://www.digikey.com/product-search/en?keywords=DF13-6S-1.25C), [Mouser](http://eu.mouser.com/ProductDetail/Hirose-Electric/DF13-6S-125C/?qs=%2fha2pyFaduhJ5h7X7LLPzEL0u%2f%252b1ZTztM8mMa9tEuYmcKFXQSgLZyQ%3d%3d))

O Conector de antena é MCX, para conectar ao cabo de antena SMA ou TNC você pode usar um dos inúmeros adaptadores ([cabo](http://www.digikey.com/product-detail/en/CAB.0130/931-1102-ND/2332729), [adaptador](http://www.digikey.com/product-detail/en/242127/ACX1348-ND/1012025))

<div style="text-align: center;"><img src="../img/reach/specs/sma-mcx-cable.jpg" style="width: 150px;"><img src="../img/reach/specs/sma-mcx-adapter.jpg" style="width: 150px;"></div><br>

### Modelo 3D

Este modelo 3D pode ser usado como referência para o designe. Por favor, note que o Reach Module vem em proteção térmica que aumenta um pouco suas dimensões externas.

<script src="https://embed.github.com/view/3d/emlid/hardware/master/Reach.STL"></script>

Durante o projeto do case, lembre-se de que você não deve colocar nada próximo a antena Wi-Fi ou o desempenho pode ser degradado. Tente deixar pelo menos 5 mm de distância para o objeto mais próximo.

### 3D cases

<div style="text-align: center;"><img src="../img/reach/specs/reach_in_case.jpg" style="width: 550px;"></div><br>


Os seguintes cases 3D imprimíveis estão disponíveis para usuários do Reach:

**Reach Module case modelo C:**

<script src="https://embed.github.com/view/3d/emlid/hardware/master/Reach_cases/Reach_case_assembly_Rev_C.STL"></script>

Download da [metade superior e inferior](https://github.com/emlid/hardware/tree/master/Reach_cases/Rev_C_parts) do case para imprimi-lo.

**Reach Module case modelo D:**

<script src="https://embed.github.com/view/3d/emlid/hardware/master/Reach_cases/Reach_case_assembly_Rev_D.STL"></script>

Download da [metade superior e inferior](https://github.com/emlid/hardware/tree/master/Reach_cases/Rev_D_parts) do case para imprimi-lo.

**Reach Module case modelo E:**

<script src="https://embed.github.com/view/3d/emlid/hardware/master/Reach_cases/Reach_case_assembly_Rev_E.STL"></script>

Download da [metade superior e inferior](https://github.com/emlid/hardware/tree/master/Reach_cases/Rev_E_parts) do case para imprimi-lo.

Para os cases de montagem D e E use o parafuso DIN-7981 (tamanho da rosca 2.2 mm, comprimento de 6.5 ou 9.5 mm). O modelo C pode ser montado usando fita adesiva.

## Especificações elétricas

### Classificações máximas

|Nome                                       | Valor                |
|-------------------------------------------|----------------------|
| Tensão de entrada nos conectores USB e DF13| 4.75 - 5.5 V         |
| Níveis lógicos em todos os pinos          | 3.3 V                |
| Tensão máxima de entrada em todos os pinos| 5.5 V                |
| Antenna DC bias                           | 3.3 V                |
| Corrente de saída da antena               | 100 mA               |
| Consumo atual máximo @5V                  | 500 mA               |
| Consumo atual normal @5V                  | 200 mA               |
| Limite atual no USB OTG                   | 1000 mA              |
| Faixa de temperatura                      | 0 +40 C (-40 +85 C)^ |

Oficialmente, a Intel Edinson está classificada entre 0°C e 40°C, mas a Intel também afirma que está realizando testes de temperatura com bons resultados, mas ainda não está pronta para classificar oficialmente a Edinson como dispositivo de faixa de temperatura estendida. O susuários relatam testes bem-sucedidos até -40°C.

### Conectores pinout
<div style="text-align: center;"><img src="../img/reach/specs/reach-connectors.png" style="width: 550px;"></div><br>

* GPIO46, GPIO77, PWM, SCL, SDA, TX, RX são conectados ao Intel Edinson via buffers e são de nível lógico de 3.3V, 5V tolerantes.
* TX e RX pertencem ao UART1 na Intel Edison
* SCL e SDA pertencem ao I2C1 no Intel Edison, o I2C1 também pode ser usado para comunicação com o magnetômetro interno no MPU9250.
* PWM pertence ao PWM3 GPIO183 na Intel Edison
* A entrada de Time Mark é conectada diretamente ao chip U-blox para baixa latência, inclui um grampo de sobretensão, resistência de corrente e resistor limitador de corrente.

### USB OTG

<div style="text-align: center;"><img src="../img/reach/specs/otg-connection.png" style="width: 550px;"></div><br>

O Reach Module pode receber energia do USB, atuando como um dispositivo e fonte de energia para a porta que atua como um host. Para usar o Reach Module no modo OTG, você precisará conectar a fonte de energia de 5V aos pinos do conector DF13 (5V, GND) e usar o cabo USB do OTG.
