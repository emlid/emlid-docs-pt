# Connecting Reach to the Internet

Conecte o Reach a internet para atualizar o ReachView para a última versão ou para receber correções de um serviço NTRIP.

??? note "Conectando o Reach a Internet via modem de celular embutido"
	##Video guide

	O vídeo abaixo apresenta o processo utilizando um cartão SIM.

	<center>

	<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/YJ2VzsKx9zQ" allowfullscreen></iframe></div>

	</center>

	## Guia de texto

	### Configuração usando cartão SIM

	!!! note ""
		Tenha um cartão SIM nano. Você pode cortar seu cartão sim no formato nano.

	* O compartimento para cartão SIM está embaixo da borracha de proteção

	!!! danger ""
		Para previnir danos ao compartimento, use-o com cuidado.

	* Empurre a proteção de metal para destravar o compartimento

	<div style="text-align: center;"><img src="../img/reachrs2/connecting-to-the-internet/1-sim-card.png" style="width: 200px;"></div>

	* Pull the cover up to open the SIM card slot

	<div style="text-align: center;"><img src="../img/reachrs2/connecting-to-the-internet/2-sim-card.png" style="width: 200px;"></div>

	* Insert your SIM card into the metallic cover

	<div style="text-align: center;"><img src="../img/reachrs2/connecting-to-the-internet/3-sim-card.png" style="width: 200px;"></div>

	* Return the slot cover into the horizontal position and slide left to lock the slot

	<div style="text-align: center;"><img src="../img/reachrs2/connecting-to-the-internet/4-sim-card.png" style="width: 200px;"></div>

	### Configurando Dados Móveis

	* Ligue o seu receptor e conecte-se a ele via app ReachView no seu dispositivo

	??? note "Conectando ao Reach via dispositivo iOS/Android"

		1. Baixe o aplicativo no [Google Play](https://play.google.com/store/apps/details?id=com.reachview) ou [Apple Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)
		2. Vá para as configurações de Wi-Fi no seu dispositivo
		3. Conecte-se ao ponto de acesso do Reach. Aparecerá como **reach:XX:XX**
		4. Digite a senha **emlidreach**
		5. Abra o aplicativo ReachView
		6. Escolha o Reach na lista

	??? note "Conectando-se através de um navegador da web em qualquer dispositivo"

		1. Vá para as configurações de Wi-Fi no seu dispositivo
		2. Conecte-se ao ponto de acesso do Reach. Aparecerá como **reach:XX:XX**
		3. Digite a senha **emlidreach**
		4. Abra um navegador da web (recomendamos usar o Chrome ou Mozilla)
		5. Digite o seguinte IP 192.168.42.1

	* Espere até que o Reach termine de ler o cartão SIM

	!!! note ""
		Se o cartão SIM necessitar de um códico PIN, o aplicativo pedirá para inserir em um pop-up. Se você não sabe o seu código PIN, contate o o provedor de serviço para conseguir esta informação.

	Você verá barras de rede indicando um cartão SIM conectando.

	* Vá na [aba Mobile data](reachview/mobile-data.md) e habilite a rede celular

	<div style="text-align: center;"><img src="../img/reachrs2/connecting-to-the-internet/mobile-data.png" style="width: 800px;"></div>

	Se tudo estiver correto, você verá as barras de rede e o tipo de conexão próximo ao ícone de bateria mostrando que os Dados Móveis estão ligados.

??? note "Conectando o Reach a Internet via Wi-FI"
	## Conectando ao ReachView
	
	??? note "Conectando ao Reach via dispositivo iOS/Android"

		1. Baixe o aplicativo no [Google Play](https://play.google.com/store/apps/details?id=com.reachview) ou [Apple Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)
		2. Vá para as configurações de Wi-Fi no seu dispositivo
		3. Conecte-se ao ponto de acesso do Reach. Aparecerá como **reach:XX:XX**
		4. Digite a senha **emlidreach**
		5. Abra o aplicativo ReachView
		6. Escolha o Reach na lista

	??? note "Conectando-se através de um navegador da web em qualquer dispositivo"

		1. Vá para as configurações de Wi-Fi no seu dispositivo
		2. Conecte-se ao ponto de acesso do Reach. Aparecerá como **reach:XX:XX**
		3. Digite a senha **emlidreach**
		4. Abra um navegador da web (recomendamos usar o Chrome ou Mozilla)
		5. Digite o seguinte IP 192.168.42.1

## Conectando-se ao Wi-Fi

* Vá para guia Wi-Fi

* Escolha a rede Wi-Fi
	
	* Escolha a sua rede se estiver visível
	
	* Se você não conseguir ver a sua rede móvel, pressione **"Connect to a hidden network"** (Conectar a uma rede oculta)

	<p style="text-align:center" ><img src="../img/reachrs2/connecting-to-the-internet/hidden-network.gif" style="width: 800px;" /></p>

* Preencha os campos para a conexão
	
	<details close>
	<summary> **Passos para conectar a rede Wi-Fi** </summary>

	Preencha o campo com a senha da rede Wi-Fi

	</details>


	<details close>
	<summary> **Passos para conectar ao ponto de acesso por dispositivos móveis** </summary>

	Para adicionar o ponto de acesso de uma rede móvel, digite o "Network name" (nome), "Security" (tipo de senha) e "Password" (senha) da sua rede Wi-Fi

	</details>


	!!! danger "Verifique a senha!"
		Você pode exibir a senha clicando no símbolo de um olho no final do campo de inserir a senha.

	<p style="text-align:center" ><img src="../img/reachrs2/connecting-to-the-internet/new-connection.gif" style="width: 800px;" /></p>

* Pressione o botão **"Connect"** (Conectar). O LED azul deve começar a piscar no Reach

		<p style="text-align:center" ><img src="../img/reachrs2/connecting-to-the-internet/network-scan.gif" style="width: 200px;" /></p>


## Processo de conexão

??? note "Passos para conectar a rede Wi-Fi"

	Se você se conectar a rede Wi-Fi, espere até que o LED de rede fique azul.
	

??? note "Passos para conectar ao ponto de acesso por dispositivos móveis"

	Se você se conectar ao ponto de acesso móvel, siga as etapas a seguir:

	* Ative o ponto de acesso Wi-Fi no seu dispositivo móvel
	* Verifique se tem o mesmo nome e senha que você preencheu na etapa anterior
	* Agora reinicie o dispositivo pressionando o botão **Power**
	* O Reach deve se conectar ao seu ponto de acesso durante a próxima inicialização


* Se a conexão for bem sucedida, o LED de rede ficará azul

		<p style="text-align:center" ><img src="../img/reachrs2/connecting-to-the-internet/client-mode.png" style="width: 200px;" /></p>

* Se a conexão falhar, o LED de rede ficará branco

		<p style="text-align:center" ><img src="../img/reachrs2/connecting-to-the-internet/hotspot.png" style="width: 200px;" /></p>

	!!! tip "Se a conexão falhar:"
		* Conecte-se ao ponto de acesso do Reach novamente
		* Verifique a senha
		* Verifique se a sua rede está configurada corretamente
		* Tente outra rede Wi-Fi


## Volte para o ReachView

??? note "Conectando-se ao Reach com dispositivos iOS/Android"
	
	1. Conecte seu dispositivo móvel à mesma rede Wi-Fi que o Reach
	2. Verifique os dispositivos Reach desponíveis
	3. Escolha o Reach na lista do aplicativo


??? note "Conectando-se através de um navegador da web de qualquer dispositivo"

	1. Conecte seu dispositivo móvel à mesma rede Wi-Fi que o Reach
	2. Use um dos software de [Varredura de rede](https://docs.emlid.com/reachrs/quickstart/#acessando-o-reach-RSRS-em-uma-rede) ou use o aplicativo ReachView para encontrar o endereço de IP do Reach
	3. Insira o endereço de IP em um navegador da web


Depois que o Reach for conectado a uma rede Wi-Fi, você poderá:

* [Atualizar o receptor](../reachview/settings/#check-app-version)
* [Conectar a NTRIP](../common/quickstart/ntrip-workflow/)
