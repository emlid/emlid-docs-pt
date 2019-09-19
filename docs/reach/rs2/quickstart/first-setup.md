## Introdução

Neste tutorial, guiaremos você pelas seguintes etapas:

* Instalar o aplicativo ReachView
* Conectar-se ao Reach RS2
* Atualizar o firmware
* Configurar a conexão entre base e rover

Para fazer isso, você precisará de um Reach RS2, uma rede Wi-Fi com acesso à internet e um smpartphone ou PC.


## Video guia

O vídeo abaixo aborda o processo da primeira atualização.

<div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/Miy8L_1AgCQ" allowfullscreen></iframe></div>

Para configurar o Reach RS2, recomendamos o uso do aplicativo ReachView. Faça o download na App Store ou no Google Play antes de atualizar.

<center>

|Google Play|App Store|
|:-------------:|:----------:|
|[App ReachView para Android [7.7 MB]](https://play.google.com/store/apps/details?id=com.reachview)|[App ReachView para iOS [7.7 MB]](https://apps.apple.com/us/app/reachview/id1295196887)|

</center>

!!! note ""
    Se você encontrar algum problema ao executar essas etapas, teremos o prazer em ajudar em nosso [**fórum da comunidade**](http://community.emlid.com/)


## Texto guia

### Ligando

Mantenha o botão Power pressionado por 3 segundos para ligar o Reach RS2. Após cerca de 30 segundos, os LEDs de energia param de piscar. O LED de rede permanecerá branco sem piscar. O Reach RS2 está agora transmitindo o seu próprio Wi-Fi.

<div style="text-align: center;"><img src="../img/quickstart/first-setup/hotspot.png" style="width: 200px;"></div>

### Conectando ao RS2

* Abra a lista de redes Wi-Fi no seu smartphone/PC

* Conecte-se a rede chamada **reach:xx:xx**

* Digite a senha: **emlidreach**


### Configurando o Wi-Fi

??? note "Usando o Reach com dispositivos iOS/Android"

    1. Faça o download do aplicativo ReachView no [Google Play](https://play.google.com/store/apps/details?id=com.reachview) ou [App Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)
    2. Abra o aplicativo e escolha o Reach na lista
    4. Toque no botão *+* e digite o nome da sua rede Wi-Fi, o tipo de segurança e a senha
    5. Toque no botão *Save*
    6. Toque na rede adicionada e depois em *Connect*

??? note "Usando o Reach em um navegador da Web em qualquer dispositivo"

    1. Inicie um navegador da Web (recomendamos o uso do Chrome ou Mozilla)
    2. Digite na barra do navegador o seguinte IP 192.168.42.1
    3. Toque no botão *+* e digite o nome da sua rede Wi-Fi, o tipo de segurança e a senha
    4. Toque no botão *Save*
    5. Toque na rede adicionada e depois em *Connect*

O Reach RS2 para de transmitir o seu Wi-Fi e se conecta à rede adicionada. 

O LED da rede piscará rapidamente ao procurar uma rede. Depois que o Reach se conectar ao Wi-Fi, o LED da rede ficará azul contínuo.

<div style="text-align: center;"><img src="../img/quickstart/first-setup/client-mode.png" style="width: 200px;"></div>

!!! note ""
    Se o seu dispositivo não se conectar a rede Wi-Fi, ele voltará ao modo hotspot (ponto de acesso).
    Nesse caso, repita as etapas e verifique novamente o nome e a senha da sua rede. 


### Acessando o dispositivo Reach RS2 em uma rede

!!! danger ""
    Verifique se o seu smartphone/PC está conectado à mesma rede Wi-Fi que o Reach.

??? note "Usando o Reach com dispositivos iOS/Android"

    1. Abra o aplicativo ReachView
    2. Atualize a lista de dispositivos
    3. Toque em **reach**


??? note "Usando o Reach com PC"

    Depois de conectar o dispositivo Reach a uma rede Wi-Fi existente, você precisará identificar o seu IP.

    Para isso, você pode usar:

    * O aplicativo "**Fing**" para [iOS](https://goo.gl/Ho0qB) ou [Android](https://goo.gl/7Wuwu)

    * ["**Nmap**"](https://nmap.org/) no Linux/OS X

    * ["**Zenmap**"](https://nmap.org/zenmap/) on Windows

    <div style="text-align: center;"><img src="../img/quickstart/first-setup/fing.png" style="width: 500px;"></div>

    * O Reach será exibido como dispositivo "**Murata Manufacturing**" ou "**AMPAK Technology**" nesses aplicativos

    * Coloque o IP do Reach na barra de endereço do navegador


### Atualizando o ReachView

Após conectar-se ao Reach RS2, você verá o ReachView Updater novamente. Aguarde até verificar se há atualizações mais recentes.

* Se houver uma atualização, pressione o botão *Update ReachView* e aguarde. Esse processo levará alguns minutos

* Quando terminar, toque em *Reboot and go to the app* para reiniciar o Reach RS2

* Aguarde o LED azul parar de piscar, mostrando que o Reach RS2 entrou na sua rede Wi-Fi novamente

Se você usar o aplicativo ReachView, deslize para a direita para voltar à lista de dispositivos, atualize a lista e toque em **reach**. Quanto ao navegador da Web, basta atualizar a página com o ReachView. Você verá o logotipo EMLID preenchendo, indicando o processo de carregamento do ReachView.

Seu Reach RS2 está pronto para o trabalho. Faça o mesmo com todas as outras unidades.

[Agora você pode configurar a conexão entre Base e Rover seguindo as intruções do nosso guia.](base-rover-setup.md)
