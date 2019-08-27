PPK significa Cinemático Pós-Processado.

### Definições e diferenças do RTK

O cinemático pós-processado (PPK) é uma técnica alternativa ao cinemático em tempo real (RTK). Com o fluxo de trabalho PPK, o posicionamento preciso não acontece em tempo real, todos os algoritmos são aplicados posteriormente. Tanto a base no solo quanto o rover (geralmente em um VANT) registram dados GNSS brutos, que são então processados para receber uma pista de posicionamento precisa.

<p style="text-align:center" ><img src="../img/reach/ppk-introduction/PPK.png" style="width: 800px;" /></p>

Embora o PPK seja usado principalmente no mapeamento de UAV, ele também pode ser usado como backup para RTK para qualquer trabalho de levantamento. O PPK oferece um fluxo de trabalho mais flexível, permitindo executar o processamento várias vezes usando configurações diferentes. Ele também não requer um link de correção entre a base e o rover, simplificando a configuração do equipamento.

### PPK para mapeamento de VANT

Existem várias vantagens de usar o PPK para mapear com um drone. O PPK não requer a implantação de Pontos de Controle no Solo (GCPs), que permite mapear áreas muito mais amplas. É especialmente útil quando você precisa mapear grandes territórios ou locais com terreno de difícil acesso.

!!! note ""
	Para o mapeamento de PPK, recomenda-se ter poucos GCPs no local para verificação de dados (pontos de verificação).

A parte mais crítica do PPK para mapeamento de UAV é a sincronização de uma câmera e o Reach M +, porque:

1. Há sempre um atraso entre o disparo da câmera e o momento em que a foto é tirada.

2. Quando um drone voa a altas velocidades, o piloto automático recebe leituras de posição apenas a cada vários metros. A precisão de 2 metros não é suficiente para o levantamento.

Reach (M+) resolve isso conectando-se a um obturador de câmera via sapata. O tempo de cada foto é registrado com uma resolução de menos de um microssegundo. Durante PPK você recebe coordenadas de momentos exatos de cada foto tirada.

Não há necessidade de integrar o Reach ao piloto automático para o mapeamento utilizando VANT.

<p style="text-align:center" ><img src="../img/reach/ppk-introduction/emlid-hotshoe.jpg" style="width: 600px;" /></p>

<p style="text-align:center" > <i>Conectando uma câmera e Reach M+ com um adaptador de sapata </i></p>

Como resultado do mapeamento PPK do VANT com o Reach, você terá um conjunto de imagens e um arquivo de texto contendo uma lista de coordenadas precisas correspondentes a cada foto. Esses dados são importados em softwares de mapeamento, como o Agisoft PhotoScan, o DroneDeploy, o Pix4d etc.

!!! tip "Solução alternativa de Drones DJI"
	Você não pode integrar facilmente o Reach M + com o DJI Mavic ou o Phantom, já que suas câmeras não têm sapata. Você pode sempre trabalhar com os GCPs, o que é simples e eficiente para pequenas áreas - assim como seu drone DJI.

Leituras adicionais:

* [Camera control](../../reachview/camera-control)
* [Logging](../../reachview/logging)
* [Pós processamento](gps-post-processing.md)
