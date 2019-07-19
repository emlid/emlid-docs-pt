## Especificações mecânicas

### Dimensões



<div style="text-align: center;"><img src="../img/reachm-plus/specs/dimensions.png" style="width: 650px;"></div><br>
<div style="text-align: center;"><img src="../img/reachm-plus/specs/height.png" style="width: 650px;"></div><br>

O peso do módulo Reach M+ é de 20g.

### Partes dos conectores

O Reach tem 4 conectores JST-GH e vem com todos os cabos necessários para conexão com outros dispositivos.

O conector de antena é MCX, para conectar os cabos de antena SMA ou TNC você pode usar um dos inúmeros adaptadores. ([cabo](http://www.digikey.com/product-detail/en/CAB.0130/931-1102-ND/2332729), [adaptador](http://www.digikey.com/product-detail/en/242127/ACX1348-ND/1012025))

<div style="text-align: center;"><img src="../img/reachm-plus/specs/sma-mcx-cable.jpg" style="width: 150px;"><img src="../img/reachm-plus/specs/sma-mcx-adapter.jpg" style="width: 150px;"></div><br>

### Modelo 3D

O modelo 3D do Reach M+ pode ser baixado aqui:

* [Reach M+ arquivo step](https://github.com/emlid/hardware/blob/master/ReachM%2B.step)


## Especificações elétricas

### Classificações máximas

|Nome                                       | Valor                |
|-------------------------------------------|----------------------|
| Tensão de entrada nos conectores USB e JST-GH | 4.75 - 5.5 V         |
| Níveis lógicos em todos os pinos          | 3.3 V                |
| Tensão máxima de entrada em todos os pinos| 3.3 V                |
| Antenna DC bias                           | 3.3 V                |
| Corrente de saída da antena               | 100 mA               |
| Consumo atual máximo @5V                  | 500 mA               |
| Consumo atual normal @5V                  | 200 mA               |
| Limite atual no USB OTG                   | 1000 mA              |
| Faixa de temperatura                      | -20…+70ºC		   |


### Conectores pinout
<div style="text-align: center;"><img src="../img/reachm-plus/specs/reachm-connectors.png" style="width: 700px;"></div><br>


### USB OTG

O Reach pode receber energia do USB, atuando como um dispositivo e fonte de energia para a porta que atua como um host. Para musar o Reach no modo OTG, você precisará conectar a fonte de alimentação de 5V aos pinos do conector JST-GH (5V, GND) e usar o cabo USB do cabo OTG.

## Conformidade

Os documentos de conformidade CE pode ser encontrados aqui:

* [Reach M+ declaração de conformidade CE](https://files.emlid.com/compliance/RM_CE_declaration.pdf)
