#Como baixar arquivos do Reach Module

Este guia descreve como fazer o download do *"System report"* (Relatório do sistema), exportar projeto de levantamento ou salvar logs do Reach Module no seu PC, laptop, tablet ou smartphone.

!!! note ""
	É necessário conectar ao ReachView através do Wi-Fi para baixar os arquivos. Dados não podem ser transferidos via USB.

##Ligando o Reach Module

Pressione o botão "Power" (Liga/Desliga) do Reach Module e espere ele ligar.

??? note "Guia Reach RS/RS+"

	Quando o LED vermelho e o LED verde ficarem sólidos, verifique o status do LED azul.

	* **O LED azul é sólido.** O Reach está no modo hotspot (roteador) e você pode conectar seu laptop ou smartphone a ele. [Clique neste link para continuar seguindo o guia.](#reach-esta-no-modo-hotspot)
	* **O LED azul pisca lentamente.** O Reach está no modo cliente e conectado à rede Wi-Fi. [Siga para esta parte do guia para continuar.](#reach-esta-no-modo-cliente)
	<br>	

	|Modo hotspot|Modo cliente|
	|:----------:|:---------:|
	|<img src="../img/quickstart/downloading-files/running-hotspot.png" style="height: 200px;">|<img src="../img/quickstart/downloading-files/running-client.gif" style="height: 200px;">|

??? note "Guia Reach RS2"

	Quando os LEDs de energia e o botão "Power" (Liga/Desliga) permanecerem sólidos, verifique o status do LED da rede.

	* **O LED de rede é branco sólido.** O Reach Module está no modo hotspot e você pode conectar seu laptop ou smartphone. [Clique neste link para continuar seguindo o guia.] (#reach-esta-no-modo-hotspot)
	* **O LED de rede está azul contínuo.** O Reach Module está no modo cliente e conectado à rede Wi-Fi. [Siga para esta parte do guia para continuar.] (#reach-esta-no-modo-cliente)
	<br>

	|Modo hotspot|Modo cliente|
	|:----------:|:---------:|
	|<img src="../img/quickstart/downloading-files/hotspot.png" style="height: 200px;">|<img src="../img/quickstart/downloading-files/client-mode.png" style="height: 200px;">|

##Conectando ao ReachView

###Reach está no modo hotspot

??? note "Conectando via aplicativo Reachview (iOS/Android device)"

	1. Baixe o aplicativo no [Google Play](https://play.google.com/store/apps/details?id=com.reachview) ou [Apple Store](https://itunes.apple.com/us/app/reachview/id1295196887?mt=8)
	2. Vá para as configurações de Wi-Fi no seu dispositivo
	3. Conecte-se ao ponto de acesso do Reach. Aparecerá como **reach:XX:XX**
	4. Digite a senha **emlidreach**
	5. Abra o aplicativo ReachView
	6. Escolha o Reach na lista


??? note "Connecting via a web browser (any device)"

	1. Vá para as configurações de Wi-Fi no seu dispositivo
	2. Conecte-se ao ponto de acesso do Reach. Aparecerá como **reach:XX:XX**
	3. Digite a senha **emlidreach**

		!!! tip "Windows OS"
			Se o Windows sugerir você entrar com um PIN a partir da etiqueta, selecione a opção **Connect using a security key instead** (Conectar utilizando chave de segurança).

	4. Abra um navegador da web (recomendamos usar o Chrome ou Mozilla)
	5. Digite o seguinte IP 192.168.42.1


### Reach is in client mode

??? note "Conectando-se ao Reach com dispositivos iOS/Android"
	
	1. Conecte seu dispositivo móvel à mesma rede Wi-Fi que o Reach
	2. Verifique os dispositivos Reach desponíveis
	3. Escolha o Reach na lista do aplicativo
	
	<div style="text-align: center;"><img src="../img/quickstart/downloading-files/Reach-list.PNG" style="width: 800px;"></div>


??? note "Conectando-se através de um navegador da web (qualquer dispositivo)"

	1. Conecte seu dispositivo móvel à mesma rede Wi-Fi que o Reach
	2. Use um dos software de [Varredura de rede](https://docs.emlid.com/reachrs/quickstart/#acessando-o-reach-RSRS-em-uma-rede) ou use o aplicativo ReachView para encontrar o endereço de IP do Reach 
	3. Inicie o navegador da web (recomendamos Chrome ou Mozilla)
	4. Insira o endereço de IP em um navegador da web


## Baixando arquivos

### Relatório do sistema

<div style="text-align: center;"><img src="../img/quickstart/downloading-files/system-report.PNG" style="width: 800px;"></div>

System reports carry important for issue resolving information about Reach settings and state. There are two types of system reports:

* **Simple report** retorna a versão do ReachView, configuração, informação de rede
* **Full report** inclui dados e registros mais técnicos do sistema

!!! attention ""
	Não recomendamos publicar o *"Full report"* (Relatório completo) em locais 'públicos', pois ele contém **informações confidenciais**, como credenciais e localização de Wi-Fi e NTRIP.

Para baixar o relatório do sistema, você só precisa [abrir a aba "Settings" (Configurações) do ReachViewto e seguir as instruções daqui.](../../reachview/settings/#relatorio-do-sistema)

### Logs

<div style="text-align: center;"><img src="../img/quickstart/downloading-files/logging.PNG" style="width: 800px;"></div>

Você pode baixar logs bem como iniciar ou parar a gravação no ReachView na aba “Logging”. [Veja a seção Logging para baixar e entender os formatos.](../../reachview/logging/#baixando-os-logs)

### Projetos

<div style="text-align: center;"><img src="../img/quickstart/downloading-files/survey.PNG" style="width: 800px;"></div>

Os projetos contém pontos que você salvou durante o levantamento RTK. Você pode encontrá-los na aba "Survey" do ReachView. [Veja este guia para aprender como exportá-los e os formatos disponíveis.](../../reachview/survey/#exportando-dados) 

##Onde encontrar o dado baixado

O download é concluído com sucesso. Para obter o arquivo, vá para a pasta onde o dispositivo salva todos os dados baixados.

###Notebook ou Desktop

Os arquivos do Reach Module geralmente são salvos por padrão na pasta **Downloads**.

###Smartphone ou tablet

* **iOS**: Depois que a mensagem "Download complete" (Download concluído) aparecer, você poderá escolher a pasta para salvar o arquivo ou compartilhá-lo usando o AirDrop ou outro aplicativo.

<div style="text-align: center;"><img src="../img/quickstart/downloading-files/download-iPad.PNG" style="width: 800px;"></div>

* **Android**: a mensagem "Download complete" (Download concluído) mostra que o arquivo foi salvo com sucesso. Geralmente os arquivos baixados estão nas pastas `Meus Arquivos/Downloads` ou `Meus Arquivos/Armazenamento Interno/Download`.

<div style="text-align: center;"><img src="../img/quickstart/downloading-files/download-Android.jpg" style="width: 800px;"></div>
