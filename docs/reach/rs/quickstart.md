### Introdução

Neste tutorial seguiremos estas etapas:

* Conectando Reach RS/RS+ em uma rede Wi-Fi
* Atualizando o ReachView pela primeira vez
* Configurando base e rover para funcionar no modo RTK com correção através do rádio LoRa

O vídeo abaixo aborda o processo da primeira atualização: ligando o Reach RS/RS+, conectar a um Wi-Fi e instalar a última versão do app ReachView. Depois de completar as instruções de vídeo contine o tutorial [montagem do Reach RS/RS+](#placing-reach-rs-module) ou através do vídeo de [configuração da Base e Rover](#base-and-rover-setup).

???+ note "Meu Reach RS/RS+ tem o adesivo do aplicativo ReachView em cima"
    <div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/fIY__hNjcNI" allowfullscreen></iframe></div>

??? note "Meu Reach RS não tem o adesivo em cima"
    <div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/HCOqtSUumow" allowfullscreen></iframe></div>


!!! Dica ""
    Se você encontrou problemas em seguir estes passos, estaremos contentes em te ajudar no nosso [**fórum da comunidade**](http://community.emlid.com/).

Este tutorial cobre apenas um caso de uso. Para obter mais informações, siga estes links:

* [Espefificações físicas](specs.md)
* [Espeficifações elétricas](specs.md)
* [•	Aplicativo ReachView](common/reachview)

## Ligando

* •	Para ligar Reach RS/RS+ segure o botão Power por 3 segundos. O LED de energia  é para mostrar que o Reach RS/RS+ está ligado. O LED de rede (azul) aceso continuamente indica que o Reach RS/RS+ está no modo ponto de acesso.

!!! Nota  ""
    Reach RS/RS+ tem bateria interna projetada para 30 horas de trabalho. O Reach RS/RS+ pode ser recarregado utilizando o cabo micro USB que o acompanha. A quantidade de carga da bateria está disponível na interface do ReachView.

## Conectando-se ao Reach RS/RS+

Quando o Reach RS/RS+ é ligado pela primeira vez, ele cria um ponto de acesso Wi-Fi.

* Abra a lista de redes Wi-Fi no seu smartphone, tablet ou laptop.

* Conecte-se a rede chamada **reach:xx:xx** (ex. reach:66:ac).

* Coloque a senha: **emlidreach**.

## Configurando Wi-Fi

Depois de conectar à rede hospedado por Reach, abra um navegador web em seu smartphone, tablet ou laptop.

* Digite  **http://reach.local** ou **http://192.168.42.1** na barra de navegação e você verá o ReachView Updater.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_updater_main.png" style="width: 350px;"></div><br>

!!! Nota ""
    Se sua interface for diferente, você precisa fazer reflash no Reach com a imagem v2.3, basta seguir [este guia](common/reachview/firmware-reflashing). Você só precisa fazer isso se o seu aparelho foi adquirido antes de 1 de março de 2017.

* Pressione o botão mais e entre com o nome da sua rede Wi-Fi, tipo de segurança e senha. Pressione o botão salvar

!!! danger "Assegurar que você está se conectando a uma rede existente (tais como wi-fi em casa, ponto de acesso do smartphone, etc)"
    Use o nome e senha da sua rede Wi-Fi. O nome da rede na imagem abaixo é um exemplo.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_updater_wifi.png" style="width: 350px;"></div><br>

* Pressione na sua rede adicionada e depois em Conectar (Connect).

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_updater_wifi_connect.png" style="width: 600px;"></div><br>

* •	Em seguida, o Reach tentará se conectar a sua rede Wi-Fi.

!!! Dica ""
    Se seu dispositivo não se conectou à rede Wi-Fi ele continuará no modo de ponto de acesso. Você pode encontrar o Reach em **http://reach.local** ou **http://192.168.42.1**.
    Verifique seu nome de rede e senha e tente novamente.

## Acessando Reach RS/RS+ conectado a rede

Após conectar o Reach a uma rede Wi-Fi existente, você precisará identificar qual é o IP dele. Você pode usar ferramentas para encontrar o IP em rede ou usar ReachView app para Android/iOS.

### Ferramentas de busca de rede

Para isto você pode usar:

* Aplicativo  "**Fing**" para  [iOS](https://goo.gl/Ho0qB) ou [Android](https://goo.gl/7Wuwu).

* ["**Nmap**"](https://nmap.org/) para Linux/OS X.

* ["**Zenmap**"](https://nmap.org/zenmap/) para Windows.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/fing.png" style="width: 500px;"></div><br>

* Reach será exibido como dispositivo "**Murata Manufacturing**" nestes aplicativos.

* Coloque o endereço de IP na barra de endereços e pronto.

Leia mais sobre encontrar o endereço de IP na [seção ReachView](common/reachview/).

### App for iOS/Android

Desde ReachView v.2.8.0 você pode se conectar ao seu Reach com um app usando seu dispositivo Android ou iOS.


| Links para download |  |
|-------------|----------|
|[Google Play](https://play.google.com/store/apps/details?id=com.reachview)|[App Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)|

Após abrir o app, você verá a lista dos receptores disponíveis em sua rede.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_ios_android.png" style="width: 400px;"></div><br>

!!! danger "Reach não pode trabalhar com ip 192.168.2.xx"
    Como a sub-rede 192.168.2.x é reservada para o Reach fazer conexões Ethernet, você precisará executar configuração inicial em um Wi-Fi diferente ou alterar as configurações do roteador. Os roteadores geralmente têm uma configuração para alterar o endereço de sub-rede, então você pode configurá-lo para 192.168.1.xx.

## Atualizando o ReachView

Depois de conectar o Reach RS/RS+ você verá ReachView Updater novamente que irá instalar as atualizações mais recentes.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_updater_finish.png" style="width: 350px;"></div><br>

* Pressione o botão Reiniciar e ir para o app! (**Reboot and go to the app!**). Aguarde enquanto o dispositivo reinicia.

* Em cerca de um minuto, atualize a página com o app ReachView.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_loading.png" style="width: 800px;"></div><br>

## Configurando Base e Rover

Este tutorial irá guiá-lo através do processo de instalação de duas unidades de Reach RS/RS+ como rover e base e vai ajudar você a configurar a comunicação entre eles via rádio LoRa no modo RTK.

<div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/4GfUDoDwEAE" allowfullscreen></iframe></div>

## Placing Reach RS/RS+ module


* Reach RS/RS+ pode ser colocado sobre um tripé com rosca de 1/4". Cada pacote vem com um adaptador para 5/8" para bastão.

!!! danger "Importante"
    **Não deve haver** nenhum obstáculo próximo à antena que possam obstruir a visão do céu superior a 30 graus acima do horizonte. Não teste o dispositivo dentro de casa ou perto de edifícios, não cubra a visão do céu das antenas com computadores portáteis, carros ou você mesmo. RTK requer satélite, boa visibilidade e recepção

Um guia de como instalar as antenas está disponível na seção [Reach RS/RS+ placement](placement).


## Trabalhando com o aplicativo ReachView

### Verificação da bateria

Você pode verificar o estado da bateria do Reach RS/RS+, clicando sobre o sinal no canto superior direito.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/battery.png" style="width: 450px;"></div><br>

### Passo a passo da interface

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_status_menu.png" style="width: 800px;"></div><br>

Menu de ReachView é composto por 9 abas, mas só precisamos de três para começar a trabalhar:

* Aba de **status** mostra os níveis atuais de satélite, parâmetros RTK, coordenadas e mapa.

* Aba do **modo base** é usado para definir o tipo de saída de correção, coordenadas da base e mensagens RTCM3.

* Aba de **entrada de correção** é usado para definir a correção da base enviada para o rover.

### Configurando a base

* Conecte-se ao Reach RS/RS+ que você deseja utilizar como base.

* Vá em configurações e mude o nome para “reach-base”. Isto irá simplificar o trabalho em campo quando você precisar alternar entre os dispositivos.

* Vá até a aba **Modo Base (base mode)** e ligue a Saída de correção (Correction output), marcando a caixa.

* Selecione a aba LoRa e configure uma frequência entre 862 MHz a 1020 MHz e selecione a potência de saída.

!!! Dica ""
    Usando a rádio LoRa é possível bater até 19km em linha de visão ou alguns km em áreas urbanas com apenas 20 dBm de potência.


!!! Aviso ""
    Certifique-se de selecionar a potência de saída apropriada e a frequência de acordo com os regulamentos locais.

* Em seguida, defina o parâmetro de intervalo (Air Rate).

!!! Dica ""
    Menor intervalo (Air Rate), maior será a distância de trabalho. A fim de desbloquear intervalos menores, desative mensagens de correção ou reduza o intervalo.

* Aplicar configurações e aguarde até que a base armazene uma posição média.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reachrs-lora-base.png" style="width: 1200px;"></div><br>


### Configurando o rover

* Conecte-se ao Segundo Reach.

* Vá em configurações e mude o nome para “reach-rover”.

* Vá até a aba **Entrada de correção (Correction input)**.

* Selecione modo de correção LoRa.

*	Frequência e intervalo (Air Rate) dever ser iguais o que foi configurado na base.

*	Aplique as mudanças e você verá que o rover está conectado a base.


<div style="text-align: center;"><img src="../img/reachrs/quickstart/reachrs-lora-rover.png" style="width: 1200px;"></div><br>

* A base agora está enviando correções para o rover via rádio LoRa no formato RTCM3.

### Informações

* •	Vá até a aba **Status** do dispositivo rover.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_status_menu_correction.png" style="width: 800px;"></div>

Você pode ver um gráfico de barras com níveis de satélite, parâmetros RTK, modo de posicionamento e status da solução, coordenadas do rover e base em formato LLH, velocidade e mapa. Neste tutorial rápido, o modo de posicionamento é definido como "Cinemático", que é o principal modo RTK.

* •	Se tudo foi configurado corretamente, **status de solução** será **Float** e **você deve ver barras cinzentas, perto das barras de níveis de satélite**.

!!! note ""
    **Float** significa que as correções da base estão sendo levadas em consideração e o posicionamento é relativo a base, mas as ambiguidades ainda não foram resolvidas.

    Se você ver “-“ ou **Autônomo (Single)** no **Status de solução** significa que algo não está correto.
“-“ significa que não há nenhuma informação para o software processar. Ou até mesmo não passou tempo suficiente ou a antena não está posicionada em um lugar com visão para o céu.

    **Autônomo (Single)** significa que o rover encontrou solução independente da base, as correções da base ainda não estão sendo levadas em consideração. Se o rover for iniciado no modo autônomo (single), este também será o resultado.


* Se tudo foi configurado corretamente e a base e o rover tiver uma boa visão do céu, você deverá ver o **status da solução** alterar para **fix** em poucos minutos. **Fix** significa que o posicionamento está relativo a base e a ambiguidade foi resolvida.

<div style="text-align: center;"><img src="../img/reachrs/quickstart/reach_view_status_menu_fix.png" style="width: 800px;"></div><br>

* •	Agora você pode ver os pontos <font color="green"> verdes </font> no mapa abaixo. Os pontos <font color="orange"> laranja  </font> são **Float**. <font color="red"> Vermelho </font> - solução **Autônomo (single)**.

* •	Você está pronto para começar!

## Mais informações

Parabéns por finalizar o tutorial guia rápido! Continue aprendendo como configurar utilizando diferentes métodos de correção [na seção ReachView](common/reachview).
