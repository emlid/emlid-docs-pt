## Demonstração de Vídeo

Uma profunda gratidão vai para o nosso usuário pró [TB_RTK](https://community.emlid.com/users/tb_rtk/activity) por uma contribuição significativa neste tutorial.

<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/yy8EVSMq9Bk" frameborder="0" allowfullscreen></iframe></div>

É possível substituir o GPS interno no seu dispositivo Android com o Reach, assim qualquer aplicativo de posicionamento poderá usar coordenadas RTK precisas. Aplicativos comumente usados são Mobile Topographer Pro e ESRI Arcgis Collector.

## Configurando o Reach

Para usar o Reach com aplicativo Android, você precisará fazer o seguinte:

* Emparelhe seu dispositivo Android com Reach / Reach RS / RS +

!!! Dica ""
    Para fazer isso, torne seu dispositivo detectável. Em seguida, vá para a aba Wifi / Bluetooth e encontre seu dispositivo na seção bluetooth. Quando seu dispositivo aparecer na seção "visível", pressione-o para enviar uma solicitação de pareamento. Aceite o pedido de pareamento no seu dispositivo. Seu dispositivo aparecerá na "seção de dispositivos pareados".

**Access Reach RS+ rover using ReachView**

??? note "Connecting to Reach with iOS/Android device"

	1. Get the app from [Google Play](https://play.google.com/store/apps/details?id=com.reachview) or [Apple Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)
	2. Go to Wi-Fi settings on your device
	3. Connect to Reach hotspot. It appears as **reach:XX:XX**
	4. Enter password **emlidreach**
	5. Launch ReachView app
	6. Choose Reach from the list

* Na aba "Position output”, defina a saída de posição para BT e formato para **NMEA**

!!! Dica ""
    Não se esqueça de aplicar as novas configurações do rover

* You should now be able to see your Android device listed as an available device. In this guide, we used a device named as **Galaxy Tab A (2017)**

<p style="text-align:center"><img src="../img/reach/mock-location/discoverable-devices.png" style="width: 800px;"/></p>

* Tap the name of the Android device in ReachView

**Back to the Android device**

* You should receive a pairing request from Reach RS+. Confirm it

<p style="text-align:center"><img src="../img/reach/mock-location/pairing-request.jpg" style="width: 800px;"/></p>

<br>

Reach RS+ and Android device are now paired:

<p style="text-align:center"><img src="../img/reach/mock-location/android-paired.jpg" style="width: 800px;"/></p>

<p style="text-align:center"><img src="../img/reach/mock-location/reachview-paired.png" style="width: 800px;"/></p>

## Position output from Reach to Android

* In ReachView app, navigate to the **Position output** screen

* Activate **Output 1**, set it to **BT** and select solution output format to **NMEA**. After that, click the **Apply** button

<p style="text-align:center"><img src="../img/reach/mock-location/position-output.png" style="width: 800px;"/></p>

!!! note ""
	You might see an error message **Send error (111)**  in some cases. This is fine as long as there is no client connected to the NMEA stream yet.

## Localização de simulação do Android

Nós fornecemos um guia sobre como usar Reach com [Lefebure NTRIP caster](https://play.google.com/store/apps/details?id=com.lefebure.ntripclient) bypor Lefebure Design.

Apesar de ser chamado de NTRIP caster, este aplicativo também permite a entrada de dados NMEA via bluetooth. Além disso, ele suporta o recurso Android chamado **mock location**, que permite substituir receptor GPS embutido do seu dispositivo com um provedor de localização externa, Reach no nosso caso.

Para conectar o Reach, faça o seguinte:

* Abra o aplicativo, vá para as configurações (engrenagem no canto superior direito)

<p style="text-align:center"><img src="../img/reach/mock-location/developer-options.jpg" style="width: 800px;"/></p>

* Então vá para as configurações do receptor

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-main-screen.jpg" style="width: 800px;"/></p>

* Go to the **Receiver Settings**

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-settings.jpg" style="width: 800px;"/></p>

!!! check "Configurações internas do receptor:"
    1. Altere o dispositivo Bluetooth para o Reach ao qual você está emparelhado
    2. Alterar o método de conexão Bluetooth para **Secure via Reflection**  
    3. Ative o **Mock Location** se você precisar  

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-receiver-settings-1.jpg" style="width: 800px;"/></p>

* Volte para a tela principal, aperte **Conectar** e veja a conexão!

!!! tip ""
	Check the log messages to confirm the Bluetooth connection got established and the information about satellites is updated.

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-connected.jpg" style="width: 800px;"/></p>

Agora as coordenadas no seu dispositivo Android são substituídas por coordenadas do Reach / Reach RS/RS + e você pode usá-las em qualquer aplicativo.
