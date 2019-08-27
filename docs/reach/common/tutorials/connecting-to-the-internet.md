# Conectando o Reach à internet

Conecte o Reach à internet para atualizar o ReachView para a versão mais recente ou para obter correções do seu serviço NTRIP.


## Conectando-se ao ReachView

??? note "Conectando-se ao Reach com dispositivos iOS/Android"

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
	
		!!! tip "Windows OS"
			Se o Windows sugerir você entrar com um PIN a partir da etiqueta, selecione a opção **Connect using a security key instead** (Conectar utilizando chave de segurança).	
	
	4. Abra um navegador da web (recomendamos usar o Chrome ou Mozilla)
	5. Digite o seguinte IP 192.168.42.1


## Conectando-se ao Wi-Fi

* Vá para guia Wi-Fi

* Escolha a rede Wi-Fi
	
	* Escolha a sua rede se estiver visível
	
	* Se você não conseguir ver a sua rede móvel, pressione **"Connect to a hidden network"** (Conectar a uma rede oculta)

<p style="text-align:center" ><img src="../img/reach/connecting-to-the-internet/hidden-network.gif" style="width: 800px;" /></p>

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

<p style="text-align:center" ><img src="../img/reach/connecting-to-the-internet/new-connection.gif" style="width: 800px;" /></p>

* Pressione o botão **"Connect"** (Conectar). O LED azul deve começar a piscar no Reach

	<p style="text-align:center" ><img src="../img/reach/connecting-to-the-internet/network-scan.gif" style="width: 400px;" /></p>


## Processo de conexão

??? note "Passos para conectar a rede Wi-Fi"

	Se você se conectar a rede Wi-Fi, espere até que o LED azul comece a piscar lentamente.


??? note "Passos para conectar ao ponto de acesso por dispositivos móveis"

	Se você se conectar ao ponto de acesso móvel, siga as etapas a seguir:

	* Ative o ponto de acesso Wi-Fi no seu dispositivo móvel
	* Verifique se tem o mesmo nome e senha que você preencheu na etapa anterior
	* Agora reinicie o dispositivo pressionando o botão **Power**
	* O Reach deve se conectar ao seu ponto de acesso durante a próxima inicialização


* Se a conexão for bem sucedida, você verá o LED azul piscando lentamente

	<p style="text-align:center" ><img src="../img/reach/connecting-to-the-internet/running-client.gif" style="width: 400px;" /></p>

* Se a conexão falhar, você verá que o LED azul permanecerá sem piscar

	<p style="text-align:center" ><img src="../img/reach/connecting-to-the-internet/running-hotspot.png" style="width: 400px;" /></p>

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
	2. Use um dos software de varredura [Network Scan](https://docs.emlid.com/reachrs/quickstart/#accessing-reach-rsrs-device-in-a-network) ou use o aplicativo ReachView para encontrar o endereço de IP do Reach 
	3. Insira o endereço de IP em um navegador da web


Depois que o Reach for conectado a uma rede Wi-Fi, você poderá:

* [Atualizar o receptor](../../reachview/settings/#verifique-a-versao-do-aplicativo)
* [Receber correções NTRIP](../../reachview/correction-input/#ntrip)
