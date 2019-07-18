## Visão geral

O QGIS (anteriormente conhecido como Quantum GIS) é um aplicativo GIS/SIG (Sistema de Informações Geográficas) de desktop de plataforma e código aberto que fornece visualização, edição e análise de dados. Pode ser usado para quase qualquer aplicativo GIS. 

<div style="text-align: center;"><img src="../img/reach/qgis-survey/reachrs-qgis.jpg" style="width: 350px;"></div><br>

## Conectando QGIS ao Reach RS/RS+

Antes de tudo, precisamos conectar o equipamento ao QGIS. Existem duas maneiras simpes. Uma através da rede local, outra via USB.

### TCP

Para conectar-se pela rede local, o computador que executa o QGIS precisa estar na mesma rede que o rover. Isso pode ser feito através do hotspot (ponto de acesso) do rover. Esta captura de tela mostra a configuração do rover Reach e a configuração do QGIS. O número da porta é o mesmo que entraremos no QGIS para encontrar a string de posição.


<div style="text-align: center;"><img src="../img/reach/qgis-survey/reach-rs-tcp-set.png" style="width: 550px;"></div><br>


No QGIS, o painel de cores fica verde para indicar a conexão quando entramos no endereço IP e porta do rover.


<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-tcp-set.png" style="width: 350px;"></div><br>


### USB

A segunda maneira de conectar é via "dispositivo serial", na verdade, USB. Primeiro, conecte o micro USB na porta do Rover.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/reachrs-usb.jpg" style="width: 550px;"></div><br>

Em seguida, conecte a porta USB do computador.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/reachrs-usb-tablet.jpg" style="width: 350px;"></div><br>

Para isto, as configuração do rover devem ser como o screenshot abaixo.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/reachview-qgis-usb.jpg" style="width: 350px;"></div><br>

No QGIS, escolha para conectar via dispositivo serial e use a mesma porta COM mostrada nos dispositivos conectados.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-usb.png" style="width: 350px;"></div><br>

Agora que estamos conectados, devemos ver nossa posição no QGIS semelhante ao aplicativo Reachview.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/reachview-qgis-connected.png" style="width: 750px;"></div><br>
<div style="text-align: center;"><img src="../img/reach/qgis-survey/reachview-qgis-connected1.png" style="width: 750px;"></div><br>

## Itens básicos do QGIS

No QGIS, podemos escolher entre uma ampla variedade de mapas de fundo, incluindo suas próprias imagens de drone.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-view.png" style="width: 550px;"></div><br>

O painel GPS mostra o status, mas se você quiser verificar o status da solução, é melhor ficar de olho no aplicativo Reachview. Quando estivermos conectados e tivermos nossas camadas e configurações prontas, podemos ir trabalhar, adicionando pontos, linhas e polígonos com base em nossa localização.


<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-emlid2.png" style="width: 350px;"></div><br>

### Ferramentas CAD no QGIS

Vamos ver o recurso de inserir linhas manualmente. Frequentemente, precisamos inserir uma linha e, em seguida, inserir as distâncias e as direções com base nessa linha, por exemplo, 30 m a 90 graus em relação a uma determinada linha. O QGIS possui um recurso chamado de ferramentas CAD que deve funcionar para isso. Primeiro, insira a linha (por exemplo, linha de propriedade). Em seguida, desenhe linhas paralelas ou perpendiculares a partir da linha inserida. Isso é encontrado no painel de digitalização avançado. Aqui você pode selecionar o ponto inicial pelo vértice e começar a desenhar a partir desse ponto em uma direção em relação a uma linha selecionada.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-cad.png" style="width: 350px;"></div><br>

Distâncias e ângulos podem ser predefinidos.
De volta ao escritório após o levantamento, há opções para cortar, estender, trabalhos com linha, converter pontos em arcos, etc. Esses recursos também podem ser usados durante o levantamento. Confira o plug-in QAD.

<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-qad-tools.png" style="width: 650px;"></div><br>

Também veja o plugin CadTools

<div style="text-align: center;"><img src="../img/reach/qgis-survey/qgis-cad-tools.png" style="width: 650px;"></div><br>

!!! tip ""
    [Veja](https://www.youtube.com/watch?v=QsjmLa16obs1) o tutorial ferramenta QGIS CAD por Klas Karlsson.


## Creditos

Agradecemos [Brent Wiebe](https://community.emlid.com/users/brent_w/activity) por compartilhar suas experiências do uso do QGIS como uma ferramenta de levantamento para o Reach RS/RS+.
