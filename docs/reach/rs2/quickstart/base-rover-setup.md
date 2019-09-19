## Video guia

Este tutorial mostrará como configurar duas unidades Reach RS2 como rover e base e como fazê-las funcionarem com o rádio LoRa no modo RTK.

Para definiar correções de base NTRIP, [siga as etapas do guia "Trabalhando com o serviço NTRIP"](../common/quickstart/ntrip-workflow.md).

<div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/-K32ayVmH6U" allowfullscreen></iframe></div>


## Texto guia

### Renomeando os dispositivos Reach

Por padrão, todo Reach tem o mesmo nome, e a primeira coisa que faremos será renomeá-los, para que seja mais fácil distinguir base e rover no campo.

!!! note "Como definir o Reach?"
    Existe uma maneira fácil de entender a qual unidade você está conectado. Basta abrir o menu e tocar no botão em forma de lâmpada. O LED do botão Power desligará e começará a piscar.

* Conecte-se ao Reach RS2 que você deseja usar como base

* Vá para configurações e altere o nome para **reach-base**. Esse nome também será usado como um rótulo da rede Wi-Fi quando o Reach estiver no modo hotspot (ponto de acesso).

* Pressione *Save*

!!! tip ""
    Use um adesivo que vêm na embalagem do Reach para marcar a unidade.

Faça o mesmo com o segundo Reach RS2. No entanto, use o nome **reach-rover** em vez de **reach-base**.


### Configurando o Reach base

Agora vamos definir as configurações RTK e a comunicação entre a base e o rover. Vamos começar com a base.

* Conecte-se à unidade base

* Abra a guia **RTK Settings** e escolha cada constelação de satélite

* Defina a taxa de atualização em 1 Hz

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-base-rtk-settings.png" style="width: 800px;"></div>


Agora vamos configurar o rádio LoRa na base Reach RS2 para transmitir correções RTK.

* Vá para a guia **Base mode** e, na seção **Corrections output**, selecione **LoRa**

* Defina a potência de saída para **20 dBm** e o air rate em **9.11 kb/s**

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-base-lora.png" style="width: 800px;"></div>

* Na lista de mensagens RTCM3, selecione a saída **ARP station coordinates** em **0.1 Hz** e as outras em **1 Hz**

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-base-rtcm3.png" style="width: 800px;"></div>

!!! danger ""
    Certifique-se de selecionar a potência e a frequência de saída apropriadas, de acordo com os regulamentos locais. Caso haja restrições, as limitações da banda de frequência serão aplicadas automaticamente.

* Aplique as configurações e aguarde até que a base calcule a média de sua posição na caixa Base coordinates


### Configurando o rover

* Conecte-se à unidade rover

* Vá para a guia **RTK settings**

* Defina o modo de posicionamento para **Kinematic**

* Selecione os mesmos sistemas GNSS da base, defina a taxa de atualização de 5 Hz e pressione *Apply*

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-rover-rtk-settings.png" style="width: 800px;"></div>

Agora vamos configurar o rádio LoRa na unidade rover para receber correções. 

* Go to **Correction input** tab

* Em **Base correction** escolha **LoRa**

* As configurações de frequência e air rate devem corresponder ao que foi configurado na base

* Aplique as alterações e você verá que o rover está conectado à base

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-rover-lora.png" style="width: 800px;"></div>

!!! tip ""
    Para garantir que as correções estejam passando da base para o rover, você pode colocar os dois receptores pela janela por alguns minutos para fornecer visibilidade ao céu. Vá para a guia Status na unidade rover. Barras coloridas estão disponíveis para os satélites disponíveis. Se o LoRa estiver configurado corretamente, eles serão acompanhados por barras cinzas. Eles representam as correções recebidas da base.


### Implantação do módulo Reach RS2

Uma vez configuradas as unidades, podemos ir para o campo. Para os trabalhos de campo, você precisará de um tripé e um bastão.

Monte o Reach RS2 da base e nivele com precisão o tripé. Coloque o rover no bastão e conecte as antenas LoRa. Ligue os dispositivos.

!!! danger "Atenção"
    Não deve haver obstáculos perto da antena que possam bloquear a visão do céu a mais de 30 graus acima do horizonte.
    **Não** teste o dispositivo em ambientes fechados ou próximos a edifícios, não cubra a vista do céu para as antenas com laptops, carros ou você mesmo. O RTK requer boa visibilidade e recepção de satélite.

Um guia sobre como posicionar corretamente as antenas está disponível na seção [Posicionando o Reach RS2](../placement.md).

Vamos configurar a base.

* Conecte-se à base

* Vá para guia **Base mode**

* Na seção **Base coordinates**, selecione **Average single** e defina o tempo médio. Quanto mais você optar por acumular dados, mais precisa será a posição da base. Não mova a base enquanto o Reach estiver acumulando dados

* Uma vez calculada a posição, pressione *Apply*

* Vá para guia **Status** na base para garantir que o ReachView mostre satélites verdes

Conecte-se ao rover e verifique a guia Status. Se tudo estiver configurado corretamente, você verá muitos satélites verdes acompanhados por barras cinzas.

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-status-correction.png" style="width: 800px;"></div>


## Visualizando os resultados

Vá para guia **Status** do aplicativo no dispositivo rover.

Abaixo do gráfico SNR, você verá o status atual da solução.

* **Single** significa que o rover encontrou uma solução mas as correções da base não são aplicadas. A precisão no modo autônomo geralmente é no nível métrico.

* **Float** significa que as correções da base agora são levadas em consideração

* **Fix** significa que todas as ambiguidades foram resolvidas e a solução RTK é precisa no nível de centímetros.

Após um curto período de tempo, o rover obtém uma solução fixa. Em bons ambientes, levará alguns segundos para obter uma solução fixa. Em condições difíceis, pode demorar um pouco mais. Quando o rover obtiver o status de correção, estamos prontos para o trabalho.

Role a guia Status para baixo para ver a sua localização em tempo real.
