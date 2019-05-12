SurvCE a partir da versão 5.06 suporta Emlid Reach RS / RS +. Neste tutorial você encontrará as informações sobre como configurar o coletor de dados executando o SurvCE / SurvPC com o Reach RS/RS+ via Bluetooth.

## Configurando a conexão Bluetooth

!!! Nota ""
    Neste tutorial, a conexão Bluetooth com o dispositivo Windows é mostrada. As etapas exatas de emparelhamento dos dispositivos podem variar em diferentes plataformas.

* No aplicativo ReachView, acesse a aba Wi-Fi / Bluetooth. Ative o Bluetooth e torne o Reach RS/RS+ sempre detectável.
<p style="text-align:center"><img src="../img/reach/survce/bt-on.png" style="width: 800px;"/></p>
<br>
* No coletor de dados, vá para as configurações de Bluetooth e selecione "Adicionar um dispositivo Bluetooth". Selecione Alcance na lista de dispositivos descobertos e confirme a conexão.
<p style="text-align:center"><img src="../img/reach/survce/windows-pairing.png" style="width: 800px;"/></p>
<br>
* Quando o emparelhamento estiver concluído, você verá o coletor de dados listado no ReachView.
<p style="text-align:center"><img src="../img/reach/survce/reachview-paired.png" style="width: 800px;"/></p>


!!! note "Solução alternativa do SO Windows para o SurvPC"
    Se você estiver usando o SurvPC no sistema Windows com adaptador Bluetooth integrado, também precisará verificar a porta COM atribuída ao dispositivo BT: <br> 1. Vá ao Painel de controle e escolha Dispositivos e Impressoras<p style="text-align:center"><img src="../img/reach/survce/control-panel.png" style="width: 600px;"/></p> <br> 2. Clique com o botão direito em Reach device e selecione Propriedades <p style="text-align:center"><img src="../img/reach/survce/properties.png" style="width: 600px;"/></p> <br> 3. Vá para a guia Hardware e marque Standard Serial over Bluetooth Link. Neste exemplo, é COM8. <p style="text-align:center"><img src="../img/reach/survce/bt-com-port.png" style="width: 400px;"/></p>



## Configurando ReachView

Após o sucesso do emparelhamento Bluetooth, você deve configurar a saída de posição (Position Output) BT e a entrada de correção (Correction input), se necessário.

### Position output (Saída de posição)

* •	Vá para “Position output” no ReachView e selecione a guia BT. Selecione o formato NMEA e clique em Aplicar.
<p style="text-align:center"><img src="../img/reach/survce/position-output.png" style="width: 800px;"/></p>


### Correction input

* Se você quiser enviar as correções do seu controlador via Bluetooth, vá para “Correction input” e selecione a aba BT. Defina o formato RTCM3 e aplique as configurações.
<p style="text-align:center"><img src="../img/reach/survce/correction-input.png" style="width: 800px;"/></p>

## Configurando SurvCE

### Configurando a comunicação entre SurvCE e Reach RS/RS+
* Depois de executar o SurvCE e criar um novo projeto, vá para a aba Equip e selecione o GPS Rover.
<p style="text-align:center"><img src="../img/reach/survce/GPS-rover.png" style="width: 600px;"/></p>
<br>
* Selecione EMLID como fabricante.
<p style="text-align:center"><img src="../img/reach/survce/emlid-reachrs.png" style="width: 600px;"/></p>
<br>
* Em seguida, vá para a aba Comms e escolha as configurações de Bluetooth.

<p style="text-align:center"><img src="../img/reach/survce/bt-configure.png" style="width: 600px;"/></p>

!!! note "Solução alternativa do SO Windows para o SurvPC"
    Se você estiver usando o SurvPC no sistema Windows com adaptador Bluetooth integrado, basta escolher Generic BT Type e selecionar a porta COM atribuída ao dispositivo BT: <p style="text-align:center"><img src="../img/reach/survce/surv-pc-com-port.png" style="width: 600px;"/></p>


* Em uma janela de diálogo, clique em "Localizar dispositivo".
<p style="text-align:center"><img src="../img/reach/survce/find-the-device.png" style="width: 600px;"/></p>
<br>
* Quando o Reach RS/RS+ for detectado, selecione-o.
<p style="text-align:center"><img src="../img/reach/survce/choose-reach.png" style="width: 600px;"/></p>
<br>
* Connect Reach RS / RS + e SurvCE.
<p style="text-align:center"><img src="../img/reach/survce/connect-bt.png" style="width: 600px;"/></p>
<br>
* Você verá a confirmação da conexão.
<p style="text-align:center"><img src="../img/reach/survce/success.png" style="width: 600px;"/></p>

### Configure o SurvCE para receber correções RTK do servidor NTRIP

* Na caixa de diálogo GPS Rover, selecione a guia RTK. Selecione “Internet da caderneta” como Dispositivo e NTRIP como Rede.
<p style="text-align:center"><img src="../img/reach/survce/NTRIP-configure.png" style="width: 600px;"/></p>
<br>
* Vá para Configurações de rede e preencha os dados do servidor NTRIP.
<p style="text-align:center"><img src="../img/reach/survce/ntrip-account.png" style="width: 600px;"/></p>
<br>
* Depois disso selecione a estação de referência e clique no botão verde.
<p style="text-align:center"><img src="../img/reach/survce/mountpoints.png" style="width: 600px;"/></p>
<br>
* A configuração terminou. Você está pronto para coletar os dados com o Reach RS/RS+ e o SurvCE!
