!!! tip ""
	O Reach Module foi substituído por [Reach M+](https://emlid.com/reach). A documentação para o Reach M+ pode ser encontrada [aqui](https://docs.emlid.com/reachm-plus/).

## Introdução

Neste guia rápido, mostraremos como configurar dois dispositivos Reach Module, um como base e um como rover com link de correção via Wi-Fi.

!!! tip ""
    Se você encontrar algum problema ao executar essas etapas, ficaremos felizes em ajudar no nosso [**fórum da comunidade**](http://community.emlid.com/).


Este tutorial cobre apenas um caso de uso. Para obter mais informações, siga estes links:

* [Especificações mecânicas](../specs/#mechanical-specs)
* [Especificações elétricas](../specs/#electrical-specs)
* [Integração de hardware](hardware-integration.md)
* [Aplicativo ReachView](common/reachview/index.md)

## Carregando

* Pegue o **Micro-USB <--> cabo USB** que vem com o pacote.

* Ligue a extremidade **Micro-USB** do cabo à porta **Micro-USB** no Reach Module e ligue a outra extremidade a uma fonte de energia de 5V, como um power bank, um adpatador de tomada USB ou uma porta USB de um computador.

!!! danger "Atenção"
    Não conecte duas fontes de energia ao mesmo tempo, pois isso pode danificar o dispositivo.

Mais sobre a fonte de energia você pode ler [aqui](power-supply.md).

## Conectando e colocando a antena GPS

* Conecte o cabo da antena a entrada MCX no Reach Module. 

* Coloque a antena em um plano de apoio. Pode ser uma chapa de metal > 100 mm de diâmetro, o teto de uma carro ou o teto de metal de um edifício. 

!!! danger ""
    No local **não deve haver** obstáculos perto da antena que possam bloquear a vista do céu 30 graus acima do horizonte.
     **Não** teste o dispositivo dentro de ambientes fechados ou perto de prédios, não cubra a visão do céu das antenas com laptops, carros ou você mesmo. O RTK requer boa visibilidade e recepção dos satélites.

Um guia sobre posicionar corretamente as antenas está disponível na seçãoA guide how to properly place the antennas is available in [Posicionamento da antena](antenna-placement.md) section.

## Conectando-se ao Reach Module

Quando o Reach Module é ligado pela primeira vez, ele cria um ponto de acesso Wi-Fi.

* Abra a lista de redes Wi-Fi no seu smartphone, tablet ou laptop.

* Conecte-se a uma rede chamada **reach:xx:xx** (ex. reach:66:ac).

* Digite a senha da rede **emlidreach**.

## Configurando o Wi-Fi

Depois de se conectar à rede hospedada pelo Reach Module, abra um navegador da web em seu smartphone, tablet ou laptop.

* Digite **http://reach.local** ou **http://192.168.42.1** na barra de endereços e você verá a tela de atualização do ReachView.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_updater_main.png" style="width: 700px;"></div><br>

!!! note ""
    Se sua inteface parecer diferente, você precisará realizar o reflash no dispositivo Reach Module com a imagem v2.3 seguindo [este guia](common/reachview/firmware-reflashing.md). Só precisa de o fazer se o seu dispositivo tiver sido comprado antes de 1 de março de 2017.

* Pressione o botão Mais e insira o nome da rede Wi-Fi, o tipo de segurança e a senha. Pressione o botão Salvar.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_updater_wifi.png" style="width: 700px;"></div><br>

* Pressione na sua rede adicionada e clique em Conectar. 

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_updater_wifi_connect.png" style="width: 600px;"></div><br>

* Depois disso, o dispositivo Reach tentará conectar na rede Wi-Fi.

!!! tip ""
    Se o seu dispositivo não se conectou à rede Wi-Fi, ele alternará para o modo de ponto de acesso.
    Você pode encontrar o Reach em **http://reach.local** ou **http://192.168.42.1**.
    Verifique o nome e a senha da sua rede e tente novamente.  

## Acessando o dispositivo Reach RS em uma rede

Depois de conectar o dispositivo Reach a uma rede Wi-Fi, você precisará identificar o seu IP. Você pode usar ferramentas de varredura de rede ou usar o aplicativo ReachView para Android/IOS. 

### Ferramentas de varredura de rede

Para isso você pode usar:

* "O aplicativo **Fing**" para [iOS](https://goo.gl/Ho0qB) ou [Android](https://goo.gl/7Wuwu).

* ["**Nmap**"](https://nmap.org/) no Linux/OS X.

* ["**Zenmap**"](https://nmap.org/zenmap/) no Windows. 

<div style="text-align: center;"><img src="../img/reach/quickstart/fing.png" style="width: 500px;"></div><br>

* O Reach será exibido como dispositivo "**Murata Manufacturing**" nesses aplicativos.

* Coloque o IP do Reach na barra de endereço e vá.

Leia mais sobre como resolver endereços de IP na seção [ReachView section](common/reachview/index.md#resolving-ip).

### Aplicativo para iOS/Android

Desde o ReachView v.2.8.0, você pode se conectar ao seu dispositivo Reach por um apolicativo usando seu dispositivo Android ou IOS.


| Links para download |  |
|-------------|----------|
|[Google Play](https://play.google.com/store/apps/details?id=com.reachview)|[App Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)|

Depois de iniciar o aplicativo, você verá a lista dos receptores disponíveis em sua rede. 

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_ios_android.png" style="width: 400px;"></div><br>

!!! danger "O Reach não pode funcionar na sub-rede 192.168.2.xx "
    Como a sub-rede 192.168.2.x é reservada dentro das conexões Reach para Ethernet, você precisará executar a configuração inicial em um Wi-Fi diferente ou alterar as configurações do roteador. Os roteadores geralmente têm uma configuração para alterar o endereço da sub-rede, portanto, você pode configurá-lo para 192.168.1.xx.


## Atualizando o ReachView

Após conectar-se ao Reach Module, você verá novamente a tela de atualização do ReachView, que instalará as atualizações mais recentes.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_updater_finish.png" style="width: 700px;"></div><br>

* Pressione o botão **Reboot and go to the app!**. Aguarde enquanto o dispositivo é reinicializado.

* Em cerca de um minuto, atualize a página com o aplicativo ReachView.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_loading.png" style="width: 800px;"></div><br>


## Trabalhando com o aplicativo ReachView


### Passo a passo da interface

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_status_menu.png" style="width: 800px;"></div><br>

O menu do ReachView consiste em 9 guias, mas só precisamos de três para começar a trabalhar.

* **Status** guia que mostra os níveis atuais de satélites, parâmetros RTK, coordenadas e mapa.

* **Base mode** guia usada para definir o tipo de saída de correção, coordenadas de base e mensagens RTCM3.

* **Correction input** guia usada para definir a entrada de correção básica para o rover.

### Configurando a estação base

* Conecte-se ao Reach Module que você deseja usar como base.

* Navegue até a guia **Base mode** e ative a opção Correction output.

* Aguarde até a média de coordenadas seja calculada na caixa Coordenadas da base.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_base_mode_menu.png" style="width: 1200px;"></div><br>

Por padrão, a saída de correção da base estará disponível em uma porta **TCP 9000**.


### Configurando o Rover

* Conecte-se ao segundo Reach Module. 

* Navegue até a guia **Correction input**. 

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_correction_input_tab.png" style="width: 800px;"></div><br>

* Escolha o modo de correção TCP.

* Esolha **Client** no campo **Role**.

* Adicione o IP base no campo **Address**.

* Adicione a porta de correção base no campo **Port**. O padrão é **9000**.

* Escolha a entrada de correção **Format**. O padrão é **RTCM3**. 

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_correction_input_tcp.png" style="width: 800px;"></div><br>

* Salve as configurações pressionando o botão **Apply**.


### Exebindo os resultados

* Vá para a guia **Status** do aplicativo no dispositivo rover.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_status_menu_correction.png" style="width: 800px;"></div><br>

Você pode ver um gráfico de barras com os níveis dos satélites, parâmetros RTK, modo de posicionamento e sataus da solução, coordenadas atuais do rover e base no formato LLH, velocidade e mapa. Neste guia rápido, o modo de posicionamento é definido como "Kinematic", que é o principal modo RTK.

* Se tudo estiver configurado corretamente, **Solution status** será **Float** e **você deverá ver barras cinzas perto das barras dos níveis de satélites**. 

!!! warning ""
    **Float** significa que as correções da base agora são levadas em consideração e o posicionamento é relativo às coordenadas da base, mas a ambiguidade não foi resolvida.  

    Se você ver **"-"** ou **Single** na caixa *Solution status** nesta etapa, isso significa que algumas configurações estão incorretas.  

    **"-"** significa que não há informações para o software processar. Não houve tempo suficiente ou a antena não foi colocada corretamente.  

    **Single** significa que o rover encontrou uma solução que depende de seu próprio receptor e as correções básicas não são levadas em consideração ainda. Se o rover for iniciado sozinho, este também será o resultado.

* Se tudo tiver sido configurado corretamente e a base e os rover tiverem bia visibilidade do céu, você deverá ver **Solution status** mudar para **Fix** em alguns minutos. **Fix** significa que o posicionamento é relativo à base e a ambiguidade foi resolvida.

<div style="text-align: center;"><img src="../img/reach/quickstart/reach_view_status_menu_fix.png" style="width: 800px;"></div><br>

* Agora você pode ver <font color="green"> pontos verde </font> no mapa abaixo. <font color="orange"> Pontos laranja</font> mostram solução **Float**. <font color="red"> POntos vermelho </font> - solução **Single**.

* Você está pronto para ir!

## Mais leitura

Parabéns por terminar o guia rápido! Continue a aprender sobre a configuração de diferentes links de correção na seção [ReachView](common/reachview/index.md).
