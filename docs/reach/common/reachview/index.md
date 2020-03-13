<p style="text-align:center"><img src="img/reachview/introduction/reachview.gif" style="width: 550px;"/></p>

## Sobre

O ReachView é um aplicativo baseado na web que permite que você assuma o controle total do módulo Reach RTK e Reach RS/RS +. É o aplicativo mais fácil de usar já criado para um sistema RTK e, além de vários recursos, possui atualizações OTA que garantem que você trabalhe constantemente com a versão atualizada do aplicativo. Ele funciona em qualquer dispositivo com um navegador e não requer conexão com a internet. O ReachView é hospedado no próprio Reach e é acessado via conexão Wi-Fi, o que o torna compatível com Windows, OSX, Linux, Android e iOS.

## Encontrando o IP

O aplicativo ReachView é exibido por meio de um navegador ou de um aplicativo nativo para iOS/Android. Para acessar o dispositivo Reach, é necessário encontrar o endereço IP do Reach na rede. Dependendo do sistema operacional e da versão do aplicativo ReachView a bordo do Reach ou do Reach RS/RS +, isso pode ser feito de diferentes maneiras.

??? note "A versão do ReachView mais antiga que v2.8.0"

    ### Quando o Reach está conectado ao Wi-Fi

    O seu dispositivo deve estar conectado na mesma rede Wi-Fi que o Reach. Reach será mostrado como dispositivo “Murata Manufacturing”.

    <p style="text-align:center"><img src="img/reachview/introduction/fing.png" style="width: 500px;"/></p>

    #### Windows
    Acesse o ReachView digitando **http://reach.local** no seu navegador. Se você mudou o nome do dispositivo, por favor digite **http://device_name.local**. Se o nome não resolver:

    - Instale o aplicativo Apple Bonjour (Já estará instalado no seu sistema de você tiver iTunes ou Skype)
    -	Encontre o endereço de IP usando ["Zenmap"](https://nmap.org/zenmap/).

    #### OSX/Linux
    Acesse o ReachView digitando **http://reach.local** no seu navegador. Se você mudou o nome do dispositivo, por favor digite **http://device_name.local**. Se o nome não resolver:

    - Encontre o endereço IP usando  [“nmap”](https://nmap.org/).

    #### iOS
    Acesse o ReachView digitando **http://reach.local** no seu navegador. Se você mudou o nome do dispositivo, por favor digite **http://device_name.local**. Se o nome não resolver:

    - Encontre o endereço IP usando **Fing** o aplicativo.

    #### Android
    O Android não suporta descrição de nomes na rede local. Você precisará encontrar o endereço IP:

    -  Encontre o endereço IP usando o aplicativo **Fing**.
    - Use o aplicativo **Network Tools**, que também pode encontrar o endereço IP do Reach quando ele estiver conectado ao seu ponto de acesso de smartphone.

    ### Quando o seu dispositivo está conectado ao ponto de acesso do Reach

    Por padrão, o Reach cria um ponto de acesso Wi-Fi e você pode se conectar a ele como a qualquer outra rede Wi-Fi. Atenção que, as vezes, o seu smartphone tentará mudar automaticamente para as ligações 3G / 4G, uma vez que o ponto de acesso Wi-Fi criado pela Reach não fornece acesso à Internet.

    +	Quando perguntado se você deseja permanecer conectado à rede sem conexão com a Internet, responda “sim”.
    + Se o seu smartphone ainda estiver em conexão 3G / 4G e houver uma marca "?" Perto do ícone de Wi-Fi, convém desativar temporariamente os dados móveis. Isso forçará seu smartphone a se conectar à rede Wi-Fi.

    **Acesse o ReachView digitando “http://reach.local” ou 192.168.42.1 no seu navegador em qualquer sistema operacional.**

??? note "A versão do ReachView é mais nova que v2.8.0"

    Desde o ReachView v.2.8.0, você pode se conectar ao seu dispositivo Reach com um aplicativo usando seu dispositivo Android ou iOS.

    <center>
        <table>
            <tr>
                <th>Download links</th>
                <th></th>
            </tr>
            <tr>
                <td><a href="https://play.google.com/store/apps/details?id=com.reachview">Google Play</a></td>
                <td><a href="https://itunes.apple.com/us/app/reachview/id1295196887?mt=8">App Store</a></td>
            </tr>
        </table>
    </center>

    Após o lançamento do aplicativo, você verá a lista dos receptores disponíveis em sua rede.

    <div style="text-align: center;"><img src="img/reachview/introduction/reach_view_ios_android.png" style="width: 400px;"></div><br>

    !!! danger "O Reach não funciona na sub-rede 192.168.2.xx"
        Como a sub-rede 192.168.2.x é reservada no Reach para conexões Ethernet, você precisará executar a configuração inicial em um Wi-Fi diferente ou alterar as configurações do roteador. Os roteadores geralmente têm uma configuração para alterar o endereço da sub-rede, portanto, você pode configurá-lo para 192.168.1.xx.

## Iniciando pela primeira vez

### Conectando ao Reach

ndo o Reach é ligado pela primeira vez, ele criará um ponto de acesso Wi-Fi.

+	Abra a lista de Wi-Fi no seu smartphone, tablet ou laptop.
+	Conecte-+e a rede chamada reach:xx:xx (ex. reach:66:ac).
+	Coloque a senha: emlidreach


### Configurando o Wi-Fi

Após conectar-se ao ponto de acesso do Reach, abra um navegador da web em seu smartphone, tablet ou laptop.

Digite http://192.168.42.1 na barra de endereços e você verá o ReachView Updater.

<p style="text-align:center"><img src="img/reachview/introduction/reach_view_updater_main.png" style="width: 350px;"/></p>

Pressione o botão + e insira o nome da rede Wi-Fi, o tipo de segurança e a senha. Pressione o botão Salvar. Isso fará com que o Reach memorize sua rede Wi-Fi.
<p style="text-align:center"><img src="img/reachview/introduction/reach_view_updater_wifi.png" style="width: 350px;"/></p>

Pressione na sua rede adicionada e clique em Conectar.
<p style="text-align:center"><img src="img/reachview/introduction/reach_view_updater_wifi_connect.png" style="width: 450px;"/></p>

O Reach tentará se conectar à sua rede Wi-Fi. Você também deve conectar seu dispositivo a essa rede.

Se o Reach não se conectar à rede Wi-Fi, ele alternará automaticamente para o modo de ponto de acesso. Tente novamente desde o começo deste capítulo. Verifique se o nome e a senha da sua rede estão corretos.

### Atualizando

Se a conexão ao Wi-Fi for bem-sucedida, você poderá [encontrar o Reach na sua rede](#resolving-ip) e abrir o ReachView. Durante a primeira configuração, você verá o ReachView Updater. É um aplicativo separado que lida com autoteste, sincronização de horário e atualizações do aplicativo principal do ReachView.
<p style="text-align:center"><img src="img/reachview/introduction/reach_view_updater_finish.png" style="width: 350px;"/></p>

O ReachView Updater verificará as atualizações de software e as instalará.

Pressione Reiniciar e vá para o app! Aguarde enquanto o dispositivo é reinicializado.

Em cerca de um minuto, atualize a página com o aplicativo ReachView.


<p style="text-align:center"><img src="img/reachview/introduction/reach_view_app.png" style="width: 800px;"/></p>
