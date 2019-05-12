## Demonstração de Vídeo

Uma profunda gratidão vai para o nosso usuário pró [TB_RTK](https://community.emlid.com/users/tb_rtk/activity) por uma contribuição significativa neste tutorial.

<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/yy8EVSMq9Bk" frameborder="0" allowfullscreen></iframe></div>

É possível substituir o GPS interno no seu dispositivo Android com o Reach, assim qualquer aplicativo de posicionamento poderá usar coordenadas RTK precisas. Aplicativos comumente usados são Mobile Topographer Pro e ESRI Arcgis Collector.

## Configurando o Reach

Para usar o Reach com aplicativo Android, você precisará fazer o seguinte:

* Emparelhe seu dispositivo Android com Reach / Reach RS / RS +

!!! Dica ""
    Para fazer isso, torne seu dispositivo detectável. Em seguida, vá para a aba Wifi / Bluetooth e encontre seu dispositivo na seção bluetooth. Quando seu dispositivo aparecer na seção "visível", pressione-o para enviar uma solicitação de pareamento. Aceite o pedido de pareamento no seu dispositivo. Seu dispositivo aparecerá na "seção de dispositivos pareados".


<p style="text-align:center"><img src="../img/reach/mock-location/bluetooth.png" style="width: 800px;"/></p>


* •	Na aba "Position output”, defina a saída de posição para BT e formato para **NMEA**

!!! Dica ""
    Não se esqueça de aplicar as novas configurações do rover

<p style="text-align:center"><img src="../img/reach/mock-location/solution.png" style="width: 800px;"/></p>

## Localização de simulação do Android

Nós fornecemos um guia sobre como usar Reach com [Lefebure NTRIP caster](https://play.google.com/store/apps/details?id=com.lefebure.ntripclient) bypor Lefebure Design.

Apesar de ser chamado de NTRIP caster, este aplicativo também permite a entrada de dados NMEA via bluetooth. Além disso, ele suporta o recurso Android chamado **mock location**, que permite substituir receptor GPS embutido do seu dispositivo com um provedor de localização externa, Reach no nosso caso.

Para conectar o Reach, faça o seguinte:

* Abra o aplicativo, vá para as configurações (engrenagem no canto superior direito)

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-main-screen.jpg" style="width: 300px;"/></p>

* Então vá para as configurações do receptor

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-settings.jpg" style="width: 300px;"/></p>

!!! check "Configurações internas do receptor:"
    1. Altere o dispositivo Bluetooth para o Reach ao qual você está emparelhado
    2. Alterar o método de conexão Bluetooth para **Secure via Reflection**  
    3. Ative o **Mock Location** se você precisar  

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-receiver-settings.jpg" style="width: 300px;"/></p>

* •	Volte para a tela principal, aperte **Conectar** e veja a conexão!

<p style="text-align:center"><img src="../img/reach/mock-location/lefebure-connected.jpg" style="width: 300px;"/></p>


Agora as coordenadas no seu dispositivo Android são substituídas por coordenadas do Reach / Reach RS/RS + e você pode usá-las em qualquer aplicativo.
