## Guia com vídeo

Este tutorial mostrará como configurar dois Reach RS/RS+ para funcionar como base e rover no modo RTK através do rádio LoRa.

Para configurar correções NTRIP, [siga os passos do guia "Trabalhando com serviço NTRIP"](../common/tutorials/ntrip-workflow.md).

<div style="text-align: center;"><iframe title="Emlid manuals" width="560" height="315" src="https://www.youtube.com/embed/4GfUDoDwEAE" allowfullscreen></iframe></div>


## Guia com texto

### Renomeando o Reach

Por padrão, cada Reach tem o mesmo nome, então a primeira coisa que faremos é renomeá-los para ficar mais fácil identificar qual é base e rover.

!!! note "Como definir o Reach?"
    Há um caminho fácil para entender qual Reach você está conectado. Basta abrir o menu e pressionar no botão da lâmpada. Todos os LEDs irão piscar simultaneamente.

* Conecte-se ao Reach RS/RS+ que deseja utilizar como base

* Vá as configurações e altere o nome para **reach-base**. Este também será o nome da rede Wi-Fi quando o Reach estiver no modo hotstop (roteador)

* Pressione *"Save"* (Salvar)

!!! tip ""
    Use o adesivo da embalagem que acompanha o Reach para marcar o receptor.

Faça o mesmo para o segundo Reach RS/RS+. Mas agora use o nome **reach-rover** ao invés de **reach-base**.


### Configurando a base

Agora vamos configurar "RTK Settings" e a comunicação entre a base e o rover. Vamos começar com a base.

* Conecte-se ao Reach base

* Abra a aba **RTK Settings** e verifique se GPS, GALILEO e GLONASS ou BeiDou estão ativos. Lembre-se da seleção de satélites da sua base, utilizaremos os mesmos no rover.

!!! note ""
    Selecione o que usar dependendo da sua localização. Enquanto GLONASS cobre grande parte do mundo, BeiDou será mais eficiente na região do Pacífico e Asia.

* Altere o "update rate" (taxa de atualização" para 1 Hz

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs-base-rtk-settings.png" style="width: 800px;"></div>

Agora vamos configurar o rádio LoRa no Reach RS/RS+ base para enviar correções RTK.

* Vá para a aba **Base mode** e na seção **Corrections output** (Envio de correção) selecione **LoRa**

* Na lista de mensagens RTCM3 selecione para enviar "GPS L1 observations" a 1 Hz, "ARP station coordinates" a 0.1 Hz, "GLONASS L1 observations" a 1 Hz e GALILEO ou BeiDou a 1 Hz

* Altere o "output power" (potência) para **20dBm** e o "air rate" (taxa de transmissão) a **9.11 kb/s**

!!! danger ""
    Tenha certeza de selecionar a potência e frequência de acordo com as regulamentações do local.

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs-base-lora.png" style="width: 800px;"></div>

* In the list of RTCM3 messages select to output GPS L1 observations at 1 Hz, ARP station coordinates at 0.1 Hz, GLONASS L1 observation at 1 Hz and GALILEO or BeiDou at 1 Hz

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs-base-rtcm3.png" style="width: 800px;"></div>

* Aplique as configurações e espere até que a média de posição seja definida na seção "Base coordinates".


### Configurando o rover

* Conecte-se ao Reach rover

* Vá a aba **RTK settings**

* Altere o "Positioning mode" para **Kinematic**, "GPS Ambiguity resolution mode" para **Fix-and-hold** e "GLONASS Ambiguity resolution mode" para **ON**

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs-rover-rtk-settings.png" style="width: 800px;"></div>

* Selecione os mesmos sistemas GNSS utilizados na base, altere "Update rate" para 5 Hz e pressione *"Apply"* (Aplicar)

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs-rover-rtk-settings2.png" style="width: 800px;"></div>

Agora vamos configurar o rádio LoRa no rover para receber correções.

* Vá a aba **Correction input** (Entrada de correção)

* Em **Base correction** (Correção da base) selecione **LoRa**

* Configurações da "Frequency" e "air rate" devem ser as mesmas configuradas na base

* Aplique as configurações e o rover se conectará a base

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs-rover-lora.png" style="width: 800px;"></div>

!!! tip ""
    Para ter certeza que as correções estão sendo enviadas da base para o rover, você pode colocar ambos receptores próximos a janela, para que tenham vista para o céu. Vá a aba "Status" no rover. Barras coloridas representam os satélites coloridos. Se a configuração do LoRa estiver correta, as barras coloridas estarão acompanhadas de barras cinzas. Estas barras indicam que o rover está recebendo correção da base.


### Onde posicionar o Reach RS/RS+

Uma vez configurados, podemos ir para campo. Para o trabalho de campo, serão necessários bastão, tripé e base nivelante. Você também pode usar um tripé de câmeras.

Para montar o Reach RS/RS+ no tripé com base nivelante ou bastão, use o adaptador que acompanha o Reach RS/RS+. Também coloque a antena LoRa.

Monte a base Reach RS/RS+ no tripé e o rover no bastão. Ligue os receptores.

!!! danger "Atenção"
    **Não podem ter** obstáculos próximo a antena que bloqueem a visão para o céu com um ângulo de 30 graus a partir do horizonte.
	**Não** teste os receptores dentro de edifícios ou próximos a construções, não obstrua a visão para o céu das antenas com notebooks, carros ou você mesmo. RTK necessita de uma boa visão do céu e recepção de sinal.

O guia de como e onde colocar a base está disponível em [Montagem Reach RS/RS+](../placement.md) section.

Vamos montar a base.

* Conecte-se a base

* Vá a aba **Base mode**

* Na seção **"Base coordinates"** (Coordenadas da base) selecione **"Average single"** (Média navegada) e selecione o tempo para a média. Quanto mais tempo armazenar dados, mais acurada será a posição da bsae. Não mova a base enquanto e após o Reach RS/RS+ acumular dados.

* Uma vez que a posição for calculada, pressione *"Apply"* (Aplicar)

* Vá a aba **Status** da base para verificar se o ReachView está mostrando as barras verdes dos satélites


Conecte-se ao rover e verifique a aba status. Se tudo estiver configurado corretamente, você verá um monte de barras de satélites verdes acompanhadas por barras cinzas.

<div style="text-align: center;"><img src="../img/quickstart/base-rover-setup/reachrs2-status-correction.png" style="width: 800px;"></div>


## Status de posição

Vá a aba **Status** no aplicativo do rover.

Abaixo do gráfico de SNR, você verá o status atual da solução.


* **Single** (autônomo) significa que o rover encontrou uma solução sozinho, sem utilizar correções enviadas pela base. A precisão neste modo é métrica

* **Float** (flutuante) significa que as correções da base estão sendo levadas em consideração

* **Fix** (fixo) significa que todas as ambiguidades foram resolvidas e a solução RTK tem precisão centimétrica

Depois de um curto período de tempo, o rover tem solução fixa e você verá o "AR ratio" aumentar. Em bons ambientes, será necessário em torno de um minuto para conseguir solução fixa. Em piores condições, pode demorar um pouco mais. Quando o rover estiver com status fixo, ele está pronto para trabalhar.

Role para baixo na aba status para ver a sua localização em tempo real.