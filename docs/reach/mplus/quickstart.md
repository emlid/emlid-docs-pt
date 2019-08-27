## Introdução

Neste guia rápido, mostraremos como configurar dois dispositivos Reach, um como base e outro como rover com link de correção via Wi-Fi.

!!! Tip ""
Se você encontrar algum problema ao executar essas etapas, ficaremos felizes em ajudar no nosso [**fórum da comunidade**](http://community.emlid.com/).



Este tutorial mostra apenas um caso de uso. Para obter mais informações, siga estes links:

* [Especificações mecânicas](../specs/#especificacoes-mecanicas)
* [Especificações elétricas](../specs/#especificacoes-eletricas)
* [Integração de hardware](hardware-integration.md)
* [Aplicativo ReachView](common/reachview/index.md)

## Carregando

* Pegue o **Micro-USB <--> cabo USB** que vem com o pacote.

* Ligue a **ponta Micro-USB** do cabo à **porta Micro-USB** do Reach e ligue a outra ponta a uma fonte de energia de 5V, como um power bank, ou um adaptador USB para tomada ou ainda uma porta USB de um camputador.

!!! danger "Atenção"
    Não conecte duas fontes de energia ao mesmoa tempo, pois pode danificar o dispositivo.

Mais sobre o alimentação você pode ler [aqui](power-supply.md).

## Conectando e colocando a antena GPS

* Conecte o cabo da antena na entrada MCX no Reach. 

* Coloque a antena em um plano de apoio. Pode ser um pedaço de metal > 100 mm de diâmetro, um teto de um carro ou um teto de metal de um prédio. 

!!! danger ""
    **Não pode ter** obstáculos perto da antena que possam bloquear a vista do céu 30 graus acima do horizonte.
    **Não** teste o dispositivo dentro de ambientes fechado ou perto de edifícios, não cubra a vista do céu das antenas com laptops, carros ou você mesmo. O RTK requer boa visibilidade e recepção por satélite.

Um guia sobre como posicionar corretamente as antenas está disponível na seção [Montando a antena](antenna-placement.md) section.

## Conectando-se ao Reach

Quando o Reach M+ é ligado pela primeira vez, ele cria um ponto de acesso Wi-Fi.

* Abra a lista de redes Wi-Fi no seu smatphone, tablet ou laptop.

* Conecte-se a uma rede chamada **reach:xx:xx** (ex. reach:66:ac).

* Digite a senha da rede **emlidreach**.

## Configurando o Wi-Fi

* Obtenha o aplicativo ReachView para o seu dispositivo móvel:

| Links para Download | |
|-------------|----------|
|[Google Play](https://play.google.com/store/apps/details?id=com.reachview)|[App Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)|

* Inicie o aplicativo e escolha o Reach M+ disponível na lista. Você verá a atela de atualização do ReachView.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_updater_main.png" style="width: 350px;"></div><br>

* Pressione o botão Mais e insira o nome da rede Wi-Fi, o tipo de segurança e a senha. Pressione o botão Salvar.

!!! danger "Assegure-se de que você está se conectando à uma rede existente (como o Wi-Fi de sua casa, o Wi-fi roteado pelo seu telefone celular, etc)"
    Use o nome e a senha da sua rede Wi-Fi. O nome da rede na imagem abaixo é um exemplo. 

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_updater_wifi.png" style="width: 350px;"></div><br>

* Pressione na sua rede adicionada e clique em "Connect" (Conectar). 

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_updater_wifi_connect.png" style="width: 350px;"></div><br>

* Depois disso, o dispositivo Reach tentará conectar a sua rede Wi-Fi.

!!! tip ""
Se o seu dispositivo não se conectou à rede Wi-Fi, ele alternará para o modo de ponto de acesso. Verifique o nome e senha da sua rede e tente novamente.


* Depois de conectar o dispositivo Reach a uma rede Wi-Fi existente, você pode se reconectar ao seu dispositivo móvel na mesma rede e ver seu Reach M+ no aplicativo ReachView do iOS/Android.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_ios_android.png" style="width: 400px;"></div><br>


Leia mais sobre como resolver endereços de IP na [Seção ReachView](common/reachview/index.md#resolving-ip).

!!! danger "O Reach não pode funcionar na sub-rede 192.168.2.xx subnet"
    Como a sub-rede 192.168.2.x é reservada dentro do Reach para conexões via Ethernet, você precisará executar a configuração inicial em um Wi-Fi diferente ou alterar as configurações do roteador. Os roteadores geralmente têm uma configuração para alterar o endereço da sub-rede, portanto, você pode configurá-lo para 192.168.1.xx.

## Atualizando o ReachView

Após conectar-se ao Reach, você verá novamente a tela de atualização do ReachView, que instalará as atualizações mais recentes.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_updater_finish.png" style="width: 350px;"></div><br>

* Pressione o botão **Reboot and go to the app!**. Aguarde enquanto o dispositivo é reinicializado.

* Em cerca de um minuto, atualize a página com o aplicativo ReachView.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_loading.png" style="width: 800px;"></div><br>


## Trabalhando com o aplicativo ReachView


### Passo a passo da interface

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_status_menu.png" style="width: 800px;"></div><br>

O menu do ReachView contém 9 guias, mas só precisamos de três para começar a trabalhar:

* **Status** guia que mostra os níveis atuais de satélites, parâmetros RTK, coordenadas e mapa.

* **Base mode** guia usada para definir o tipo de saída de correção, coordenadas de base e mensagens RTCM3.

* **Correction input** guia usada para definir a correção básica para o rover.

### Configurando a base

* Conecte-se ao Reach que você deseja usar como base.

* Navegue até a guia **Base mode** e ative a opção Correction output.

* Espere até que a média das coordenadas para base seja calculada.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_base_mode_menu.png" style="width: 1200px;"></div><br>

Por padrão, a saída de correção estará disponível em uma porta **TCP port 9000**.


### Configurando o rover

* Conecte-se ao segundo Reach. 

* Navegue até a guia **Correction input**. 

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_correction_input_tab.png" style="width: 800px;"></div><br>

* Escolha o modo de correção TCP.

* Escolha **Client** no campo **Role**.

* Adicione o IP base no campo **Address**.

* Adicione a porta de correção base no campo **Port**. O padrão é **9000**.

* Escolha a entrada de correção **Format**. O padrão é **RTCM3**. 

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_correction_input_tcp.png" style="width: 800px;"></div><br>

* Salve as configurações pressionando o botão **Apply**.


### Resultados

* Vá para a guia **Status** do aplicativo no dispositivo rover.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_status_menu_correction.png" style="width: 800px;"></div><br>

Você pode ver um gráfico de barras com níveis de satélites, parâmetros RTK, mode de posicionamento e status da solução, coordenadas atuais do rover e base no formato LLH, velocidade e mapa. Neste guia rápido, o modo de posicionamento é definido como "Kinematic", que é o principal modo RTK.

* Se tudo tiver sido configurado corretamente, o **Solution status** será **Float** e **você deverá ver barras cinzas perto das barras de nível dos satélites**. 

!!! warning ""
    **Float** significa que as correções da base agora são levadas em consideração e o posicionamento é relativo às coordenadas da base, mas a ambiguidade não foi resolvida. 

    Se você ver **"-"** ou **Single** na caixa **Solution status** nesta etapa, isso significa que algumas configurações estão incorretas. 

    **"-"** significa que não há informações para o software processar. Não houve tempo suficiente ou a antena não foi colocada corretamente. 

    **Single** significa que o rover encontrou uma solução que depende de seu próprio receptor e as correções básicas não são levadas em consideração ainda. Se o rover for iniciado sozinho, este também será o resultado.

* Se tudo tiver sido configurado corretamente e a base e o rover tiverem boa visibilidade do céu, você deverá ver **Solution status** mudar para **Fix** em alguns minutos. **Fix** significa que o posicionamento é relativo à base e a ambiguidade foi resolvida.

<div style="text-align: center;"><img src="../img/reachm-plus/quickstart/reach_view_status_menu_fix.png" style="width: 800px;"></div><br>

* Agora você pode ver <font color="green"> pontos verde </font> no mapa abaixo. <font color="orange"> Pontos laranja </font> mostram solução **Float**. <font color="red"> Pontos vermelho </font> - mostram solução **Single**.

* Você está pronto para ir!

## Documentos complementares

Parabéns por terminar o guia rápido! Continue a aprender sobre a configuração de diferentes links de correção na [seção ReachView](common/reachview/index.md).
