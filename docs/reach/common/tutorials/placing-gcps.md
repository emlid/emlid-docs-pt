# Colocando GCP's no modo RTK

Para colocar GCPs com o Reach, siga as etapas deste guia.

### Configure o RTK

??? note "Configurando RTK na base Reach RS2 e rover usando do rádio LoRa"

	Se você possui 2 Reach RS2, este vídeo ensinará como configurá-los no modo RTK:

    <center>

	<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/-K32ayVmH6U" allowfullscreen></iframe></div>

	</center>

??? note "Configurando Reach RS+ base e rover RTK via rádio LoRa"

	Se você tem 2 Reach RS/RS+, configure RTK seguinte este vídeo "Configuração base e rover":
        
	<center>

	<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/4GfUDoDwEAE" allowfullscreen></iframe></div>

	</center>

??? note "Configurando RTK no Reach via NTRIP"
	Se você tem apenas um receptor Reach, você precisa conectar primeiro ao servidor NTRIP. [Veja este tutorial para mais detalhes](../../tutorials/ntrip-workflow/)

### Criar um projeto

Crie um projeto com a ferramenta de levantamento do ReachView [seguindo o guia "Criando um novo projeto".](../../reachview/survey/#criando-um-novo-projeto)

### Posicione-se no alvo

Posicione o seu bastão no centro do alvo.

<div style="text-align: center;"><img src="../img/reach/placing-gcps/placing-gcp.jpg" style="width: 800px;"></div>

!!! tip ""
	Nivele o seu bastanto utilizando a bolha.


### Armazene o ponto

Na ferramenta de levantamento do ReachView, pressione o botão *"Collect"* (Coletar) e salve seu GCP. Repita o procedimento para quantos GCPs forem necessários.

!!! tip ""
	[Mais informações sobre a ferramenta de levantamento você pode encontrar aqui](../../reachview/survey/)

### Exportar

* Especifique o formato de dados GCPs com o qual o seu software GIS ou fotogramétrico aceita
* [Exporte o arquivo do seu projeto em um dos formatos disponíveis](../../reachview/survey/#exportando-dados)
