## Introdução

Neste tutorial seguiremos estas etapas:

* Instalar o aplicativo ReachView
* Conectar ao Reach RS/RS+
* Realizar a atualizaçao do firmware
* Configurar a conexão base e rover

Para fazer isto, você precisa de um Reach RS/RS+, uma rede Wi-Fi com acesso a internet e um smartphone ou PC.


## Guia com vídeo

O vídeo abaixo apresenta todo o processo da primeira atualização.

<center>

???+ note "Reach RS/RS+ tem o adesivo do ReachView app em cima"
    <div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/fIY__hNjcNI" allowfullscreen></iframe></div>

</center>

Se o seu Reach RS/RS+ veio com o adesivo QR code em cima, ele suporte o aplicativo ReachView. Baixe da App Store ou Google Play antes de atualizar.

<center>

|Links para download||
|:-------------:|:----------:|
|[Google Play](https://play.google.com/store/apps/details?id=com.reachview)|[App Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)|

</center>

Se não tem nenhum adesivo, a unidade pode ter uma versão do firmware mais antiga. Por favor veja este vídeo.

??? note "Reach RS/RS+ não tem adesivo em cima"
    <div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/HCOqtSUumow" allowfullscreen></iframe></div>

!!! note ""
    Se você encontrou qualquer problema ao realizar estas etapas, estaremos felizes em ajudá-lo no nosso [**fórum da comunidade**](http://community.emlid.com/)


## Guia com texto

### Ligando

Para ligar Reach RS/RS+ segure o botão Power por 3 segundos. Após aproximadamente 30 segundos o LED azul irá parar de piscar. Reach RS/RS+ agora está transmitindo sinal Wi-Fi (Como um roteador!).

<div style="text-align: center;"><img src="../img/quickstart/first-setup/running-hotspot.png" style="width: 350px;"></div>

### Conectando-se ao Reach RS/RS+

* Abra a lista de redes Wi-Fi no seu smartphone/PC

* Conecte-se a rede chamada **reach:xx:xx** (ex. reach:66:ac)

* Coloque a senha: **emlidreach**


### Configurando o Wi-Fi

??? note "Usando Reach com dispositivo iOS/Android"

    1. Baixe o aplicativo do [Google Play](https://play.google.com/store/apps/details?id=com.reachview) ou [App Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)
    2. Abra e escolha o Reach na lista
    3. Pressione o botão *+* e insira o "Network name" (nome), "Security" (tipo de senha) e "Password" (senha) da sua rede Wi-Fi
    4. Pressione o botão *"Save"* (Salvar)
    5. Pressione na rede adicionada e depois em *"Connect"* (Conectar)

??? note "Usando Reach no navegador da web de qualquer dispositivo"

    1. Inicie o navegador da web (recomendamos Chrome ou Mozilla)
	2. Vá para 192.168.42.1
    3. Pressione o botão *+* e insira o "Network name" (nome), "Security" (tipo de senha) e "Password" (senha) da sua rede Wi-Fi
    4. Pressione o botão *"Save"* (Salvar)
    5. Pressione na rede adicionada e depois em *"Connect"* (Conectar)

O Reach RS/RS+ irá parar de transmitir Wi-Fi e conectará na sua rede. 

O LED azul pisca rapidamente quando ele está procurando por rede. Quando ele conectar a rede Wi-Fi, o LED piscará mais devagar. 

<div style="text-align: center;"><img src="../img/quickstart/first-setup/running-client.gif" style="width: 350px;"></div>

!!! note ""
    Se o seu dispositivo não conectar a rede Wi-Fi, ele voltará para o modo hotstop (roteador). 
	Neste caso, repita as etapas novamente e verifique se o nome e senha da sua rede estão corretos. 


### Acessando o Reach RS/RS+ em uma rede

!!! danger ""
    Tenha certeza que o seu smartphone/PC está conectado a mesma rede Wi-Fi do Reach.

??? note "Usando o Reach com dispositivo iOS/Android"

    1. Abra o aplicativo ReachView
    2. Atualize a lista de dispositivos
    3. Pressione no **reach**


??? note "Usando Reach com o PC"

    Após conectar o Reach a rede Wi-Fi existente, você precisará identificar o IP dele.

    Para isto você pode usar:

    * Aplicatigo "**Fing**" para [iOS](https://goo.gl/Ho0qB) ou [Android](https://goo.gl/7Wuwu)

    * ["**Nmap**"](https://nmap.org/) no Linux/OS X

    * ["**Zenmap**"](https://nmap.org/zenmap/) no Windows

    <div style="text-align: center;"><img src="../img/quickstart/first-setup/fing.png" style="width: 500px;"></div>

    * Reach será exibido como dispositivo "**Murata Manufacturing**" ou "**AMPAK Technology**" nestes aplicativos.

    * Digite o endereço de IP na barra de endereços e pronto.


### Updating ReachView

Após conectar ao Reach RS/RS+, você verá o ReachView Updater novamente. Espere até que ele verifique se há atualizações disponíveis.

* Se houver atualização, pressione *"Update ReachView"* (Atualizar ReachView) e espere. Este processo demora alguns minutos

* Quando concluir, pressione *"Reboot and go to the app"* (Reiniciar e ir para o aplicativo) para reiniciar o Reach RS/RS+

* Espere pelo LED azul começar a piscar devagar, mostrando que o Reach conectou-se a sua rede Wi-Fi novamente

Se você usa o aplicativo ReachView deslize para a direita para voltar a lista dos dispositivos, atualize a lista e pressione no **reach**. Para o navegador da web, basta atualizar a pagina do ReachView. Você verá o logo da EMLID ser preenchido quando estiver carregando o ReachView.

O seu Reach RS/RS+ está pronto para trabalhar. Faça o mesmo para os outros dispositivos.

[Agora você pode configurar a conexão base e Rover seguindo as instruções deste guia.](base-rover-setup.md)
