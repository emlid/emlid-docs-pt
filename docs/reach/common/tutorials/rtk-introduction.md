RTK é uma técnica usada para melhorar a precisão do receptor GNSS. Os receptores GNSS tradicionais, como o de um smartphone, só podem determinar a posição com uma precisão de 2-4 metros. O RTK pode lhe dar precisão centimétrica.

Os receptores GNSS medem quanto tempo leva para um sinal viajar de um satélite para o receptor. Os sinais transmitidos viajam através da ionosfera e atmosfera e são retardados e perturbados no caminho. Por exemplo, o tempo de viagem em um dia nublado e em condições de céu claro seria diferente. É por isso que é difícil para um receptor independente determinar precisamente sua posição. O RTK é uma tecnologia que resolve esse problema.

## Alta precisão em tempo real

Dois receptores são usados no modo RTK. Um dele estático, e o outro se movendo. Eles são chamados de estação **base** e **rover**.

<p style="text-align:center" ><img src="../img/reach/rtk-introduction/base-rover.jpg" style="width: 800px;" /></p>

A missão da Base é ficar em um lugar, calcular distorções nos sinais de satélites e enviar correções para um receptor em movimento. O Rover usa esses dados para alcançar a posição precisa, na casa do centímetro. Qualquer número de rovers pode se conectar a uma base se suas configurações de entrada corresponderem à saída da base.

<p style="text-align:center" ><img src="../img/reach/rtk-introduction/multiple-rovers.jpg" style="width: 800px;" /></p>

## Correções via NTRIP

Você não precisa necessariamente de um segundo receptor para o RTK o tempo todo. Geralmente, existem serviços locais que enviam correções de base via Internet. Essa tecnologia é chamada NTRIP.

O NTRIP é uma boa opção para áreas com boa cobertura 3G/LTE e uma rede de bases NTRIP próximas. Em outros casos, usar o segundo receptor como uma estação base local tem duas vantagens:

* autonomia em áreas remotas, pois não há necessidade de conexão com a Internet
* independência de fornecedores locais, sem taxas adicionais pelo serviço NTRIP

<p style="text-align:center" ><img src="../img/reach/rtk-introduction/NTRIP-corrections.jpg" style="width: 800px;" /></p>

## Receptores de simples e multi-frequência

No grosso modo, existem dois tipos de receptores: simples frequência (L1) e multi-frequência (L1/L2 ou mais). Suas diferenças vêm da quantidade de dados que eles podem receber dos satélites.

Por exemplo, ajuda a aumentar a distância máxima entre a base e o rover, também chamado de **linha de base**:

<center>

|     | Máxima linha de base simples frequência | Máxima linha de base multi-frequência |
|:---:|:------------:|:------------:|
| RTK | 10 km | 60 km |
| PPK | 30 km | 100 km |

</center>

O receptor multi-frequência também é muito mais robusto no que diz respeito à vista do céu. Ele pode manter a precisão do centímetro, mesmo se você operar em condições desafiadoras: floresta, cidade, locais de mineração, pedreiras, etc.

<br>

Leituras adicionais:

* [Como funciona o PPK](ppk-introduction.md)
* [Montando a base base](placing-the-base.md)
* [Trabalhando com o serviço NTRIP](../quickstart/ntrip-workflow.md)
