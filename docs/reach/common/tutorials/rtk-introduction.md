### O que é o Reach e para que serve?

O Reach é um receptor GNSS RTK para aplicações quando o seu GPS padrão com vários metros de precisão não é suficiente. Ele depende da tecnologia RTK (cinemática em tempo real) para fornecer precisão em nível centimétrico.

O RTK existe a um longo tempo, usado principalmente por topógrafo. Se você precisasse de posicionamento preciso centimétrico, precisaria gastar milhares de reais em um sistema RTK. Com o Reach, queremos mudar isso.

O Reach roda um software de processamento RTK de código aberto chamado RTKLIB escrito por Tomoji Takasu. Anteriormente, era necessário um computador para executar o RTKLIB, mas agora todos os recursos do RTKLIB estão disponíveis diretamente no Reach.

### WhatO que é um RTK?

RTK é uma técnica usada para melhorar a precisão do sistema GPS. Receptores GPS tradicionais, como um que você pode encontrar em seu smartphone, ou na maioria das plataformas robóticas, só poderiam determinar sua posição com precisão de 2-4 metros. O RTK pode dar-lhe centímetros.

Todo o sistema GPS é baseado na medição de quanto tempo leva para um sinal viajar de um satélite para o receptor. Conhecendo as órbitas precisas dos veículos espaciais - as efemérides, e pelo menos 4 tempos de viagem - pode-se determinar sua posição no planeta. Dado que a frequência da portadora GPS L1 é de 1575 MHz, cada onda tem cerca de 19 cm de comprimento. Um receptor também mede a fase de portadora de cada um dos sinais. Teoricamente, isso deveria nos dar precisão milimétrica, então por que ainda temos que lutar com precisão de 2-4 metros? Quais são as fontes de erro e o que podemos fazer para removê-las?

Os satélites orbitam a 20 200 km acima da superfície da Terra. Os sinais transmitidos viajam através da ionosfera e atmosfera e são retardados e perturbados no caminho. Por exemplo, o tempo de viagem em dia nublado e em condições de céu claro seria diferente! Muitos fatores podem aumentar o erro de posição, o melhor é que podemos supor que esses fatores não mudam muito em uma área.

Existem sistemas de aumento de GPS (DGPS), como SBAS ou WAAS, que medem as perturbações do sinal de corrente em muitas estações de controle terrestre em todo o mundo, construindo um modelo de propagação de erros e transmitindo correções através de satélites ou rádio. Muitos receptores comerciais podem usar esses sinais para precisão submétrica. Mas o que fazer se você quiser se aproximar de centímetros?

A tecnologia que nos permite fazer isso é chamada RTK (cinemática em tempo real). Dois receptores são usados, um deles é estacionário e é chamado de “estação base”, o outro é “rover”. A estação base mede os erros e, sabendo que está parada, transmite correções ao rover. A ideia é simples, mas não a matemática. Os sistemas comerciais podem chegar a precisões centimétricas e custariam uma fortuna (R$ 60 mil).

Além disso, se você não precisa das coordenadas precisas em tempo real, basta gravar os dados do rover e da base e processá-los posteriormente, eliminando assim a necessidade de uma transmissão de rádio constante. Esse método é chamado de pós-processamento e é o mais preciso entre todos.

** Comparação de coordenadas RTK e autônomas **

*Modo estático:*

<p style="text-align:center" ><img src="../img/reach/rtk-introduction/reach-static-rtk-demo.png" style="width: 800px;" /></p>

*Modo cinemático:*

<p style="text-align:center" ><img src="../img/reach/rtk-introduction/reach-kinematic-rtk-demo.png" style="width: 800px;" /></p>
