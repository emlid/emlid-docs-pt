#Trabalhando com serviço NTRIP

##Visão geral

Este guia explica como configurar o Reach para receber mensagens de correção de um serviço NTRIP.

!!! tip ""
	A configuração da entrada de correção NTRIP pode ser feita em casa antes do levantamento. Nesse caso, você só precisa conectar o Reach à Internet em campo.

##Atualize o Reach

Se você acabou de receber seu Reach, precisará atualizá-lo para ter todos os recursos mais recentes. A instrução está no estojo de transporte do Reach.

Você também pode ver o tutorual [primeira configuração](../../../quickstart/first-setup) e no [canal da Emlid no YouTube](https://www.youtube.com/watch?v=fIY__hNjcNI).

##Conecte o Reach a Internet

O Reach requer conexão com a Internet para utilizar o NTRIP. Você não precisa de nenhum dispositivo ou software especial para isso, apenas um smartphone com um recurso de ponto de acesso (roteador).

Ative os dados móveis no seu smartphone e compartilhe-os através do ponto de acesso Wi-Fi. O Reach se conectará à sua rede e terá acesso à Internet.

[Consulte o tutorial para obter mais informações sobre como conectar o Reach a outras redes.](../../tutorials/connecting-to-the-internet/)

##Configure o Reach para o modo RTK com NTRIP

Abra o ReachView e vá para **"RTK settings"**. Defina tudo para as mesmas opções da imagem abaixo.

!!! note ""
	Na seção **"GNSS select"**, escolha GALILEO ou BeiDou, dependendo da sua localização. Enquanto GLONASS cobre a maior parte do mundo, BeiDou pode ser mais eficiente na região do Pacífico e Ásia. Neste exemplo, usamos o GLONASS.

Aplique as mudanças.

<div style="text-align: center;"><img src="../img/quickstart/ntrip-workflow/rtk-settings.png" style="width: 800px;"></div>

Agora vá para a aba **"Correction input"** (Entrada de correção), selecione **NTRIP** e preencha as informações do seu provedor. Escolha a estação de referência mais próxima para receber as correções.

!!! tip ""
	Consulte o site do seu provedor NTRIP para descobrir qual Estação de Referência é melhor para sua localização.

<div style="text-align: center;"><img src="../img/quickstart/ntrip-workflow/ntrip-correction-input.png" style="width: 600px;"></div>

!!! note ""
	Se você está usando serviço VRS, você deve ativar as mensagens GGA.

Pressione **"Apply"** (Aplicar).

##Reach em um local com visão limpa para o céu

Reach RS/RS+ precisa ter uma visão limpa do céu aproximadamente 30 graus acima do horizonte. Não deve haver obstáculos que possam bloquear a visão, como prédios, árvores, carros, seres humanos, laptops etc.

<div style="text-align: center;"><img src="../img/quickstart/ntrip-workflow/skyview-obstacles.png" style="width: 800px;"></div>

[Saiba mais sobre a montagem e configuração do Reach RS+](https://docs.emlid.com/reachrs/placement/)

##Coleta e exportação dos dados

Confira os tutoriais sobre como criar novos projetos, coletar e locar pontos, importar e exportar projetos:

* [Novo projeto](../../reachview/survey/#criando-um-novo-projeto)
* [Interface do projeto](../../reachview/survey/#interface-do-projeto)
* [Coleta de ponto](../../reachview/survey/#coletando-pontos)
* [Locação](../../reachview/survey/#locacao-de-pontos)
* [Importar](../../reachview/survey/#importando-pontos) e [exportar projeto](../../reachview/survey/#exportando-dados)

