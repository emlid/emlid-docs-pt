## Especificações mecânicas

### Dimensões



<div style="text-align: center;"><img src="../img/reachm-plus/specs/dimensions.png" style="width: 650px;"></div><br>
<div style="text-align: center;"><img src="../img/reachm-plus/specs/height.png" style="width: 650px;"></div><br>

O módulo Reach M+ pesa 20g.

### Partes dos conectores

O Reach tem 4 conectores JST-GH e vem com todos os cabos necessários para conexão com outros dispositivos.

O conector de antena é MCX, para conectar o cabo de antena SMA ou TNC você podê usar um dos inúmeros adaptadores. ([cabo](http://www.digikey.com/product-detail/en/CAB.0130/931-1102-ND/2332729), [adaptador](http://www.digikey.com/product-detail/en/242127/ACX1348-ND/1012025))

<div style="text-align: center;"><img src="../img/reachm-plus/specs/sma-mcx-cable.jpg" style="width: 150px;"><img src="../img/reachm-plus/specs/sma-mcx-adapter.jpg" style="width: 150px;"></div><br>

### Modelo 3D

O modelo 3D do Reach M+ pode ser baixado aqui:

* [Reach M+ Step file](https://github.com/emlid/hardware/blob/master/ReachM%2B.step)


## Especificações elétricas

### Estimativas máximas

|Nome                                       | Valor                |
|-------------------------------------------|----------------------|
| Voltagem de entrada nos conectores USB e JST-GH  | 4.75 - 5.5 V         |
| Níveis lógicos em todos os pinos          | 3.3 V                |
| Voltagem máxima de entrada em todos os pinos     | 3.3 V                |
| Antena DC bias                            | 3.3 V                |
| Corrente de saída da antena               | 100 mA               |
| Corrente máxima consumível @5V            | 500 mA               |
| Corrente normal consumível @5V            | 200 mA               |
| Corrente limite no USB OTG                | 1000 mA              |
| Faixa de temperatura                      | -20…+70ºC		   |


### Conectores pinout
<div style="text-align: center;"><img src="../img/reachm-plus/specs/reachm-connectors.png" style="width: 700px;"></div><br>


### USB OTG

O Reach pode receber energia na entrada USB, atuando como dispositivo e fonte de energia para a porta que atua como host. Para usar o Reach no modo OTG, você precisará conectar a fonte de energia de 5V aos pinos do conector JST-GH (5V, GND) e usar o cabo USB OTG.

## Conformidade

Os documentos de conformidade CE podem ser encontrados aqui:

* [Declaração de conformidade CE para o Reach M+](https://files.emlid.com/compliance/RM_CE_declaration.pdf)
