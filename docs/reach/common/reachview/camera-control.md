Reach Module é capaz de disparar câmeras, bem como registrar eventos. Recurso de marcar um evento é indispensável para mapeamento aéreo, pois permite para registrar o tempo exato quando o obturador foi ativado.

<p style="text-align:center" ><img src="../img/reachview/camera_control/camera.png" style="width: 800px;" /></p>

### Camera trigger
Disparador da câmera é apenas disponível no módulo Reach e Reach M+ e não está disponível no Reach RS. Alterando o modo de trabalho e o tempo de disparo, você pode encontrar as configurações necessárias para disparar sua câmera. Gráfico de sinal em tempo real é mostrado na mesma página. Nota, este recurso não deve ser usado se seu piloto automático é capaz de acionar a câmera, pois tem mais informações sobre o plano de voo e pode tomar decisões mais embasadas em relação ao disparo da câmera.

### Camera events
Você vê o tempo do último registro para depuração em tempo real. Só funciona com satélites GNSS na vista de sincronização de tempo. Um registro é acionado por um pino marcador de tempo, geralmente uma sapata da câmera. É possível conectar Reach M+ com um [adaptador para qualquer câmera](#conectando-reach-m-a-uma-camera-utilizando-hsa) com sapata (por exemplo, Sony, Canon, Nikon). Todos registros são armazenados nos dados brutos. Pino marcador de tempo é projetado para ser conectado diretamente a um cabo de sapata sem quaisquer peças eletrônicas adicionais tais como resistores ou capacitores.

#### Conectando Reach M+ a uma câmera utilizando HSA

Para conectar o Reach Module uma câmera com adaptador de sapata (HSA) use cabo de 5 pinos JST-GH. Certifique-se de que ligar o adaptador a uma sapata de uma câmera corretamente:

<p style="text-align:center" ><img src="../img/reachview/camera_control/emlid-hotshoe.jpg" style="width: 500px;" /></p>

Conecte o conector JST-GH a porta С1 no Reach M+.

<p style="text-align:center" ><img src="../img/reachview/camera_control/s1port-connection.jpg" style="width: 500px;" /></p>

!!! danger "Atenção"
    Verifique a seção [RTK Settings](../../reachview/rtk-settings/#selecao-de-gnss-de-acordo-com-o-registro) dos documentos ReachView para seleção recomendada de GNSS ao registrar marcadores com o Reach.
