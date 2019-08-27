Você pode coletar pontos com o aplicativo ReachView usando a ferramenta Point Collection. O recurso permite criar uma lista de pontos baseada no projeto, estes pontos podem serem salvos automáticamente ou manualmente e os dados podem ser exportados em diferentes formatos. 

!!! tip ""
    A ferramenta é perfeita para levantamentos e coleta de pontos de controle em campo.

###Criando um novo projeto

* No aplicativo ReachView selecione o dispositivo Reach utilizado como Rover
* Escolha a guia Survey no menu
* Para criar um novo projeto, pressione **"New project"** (Novo projeto) ou clique no nome do projeto para abri-lo

<p style="text-align:center" ><img src="../img/reachview/survey/create-new-project.gif" style="width: 800px;" /></p>


###Configurações do projeto 

####Informações básicas

Na primeira etapa, você pode preencher o "Project name" (Nome do projeto), "Author" (Autor) e adicionar um "Comment" (Comentário), se quiser. No entanto, você pode usar as configurações padrão e pressionar o botão **"Next"** (Próximo).

<p style="text-align:center" ><img src="../img/reachview/survey/step1-fill-in.gif" style="width: 800px;" /></p>

####Regra para salvamento automático

As opções para salvar pontos automaticamente são definidas pelos status Single, Float ou Fix e permitem automatizar o processo de coleta de pontos. 

Para configurar a coleta de pontos automaticamente:

* Selecione o status da solução no qual o dispositivo coletará os pontos automaticamente clicando na caixa de seleção
	
	O menu com as configurações será aberto. Você pode usar os valores padrão recomendados para o tempo de observação, precisão e DOP ou definir os seus valores.

	#####Tempo de observação padrão
	| Status da solução  | Tempo |
	| :-------------: | :-------------: |
	| Fix  | 40 sec  |
	| Float  | 5 min  |
	| Single  | 10 min  |

	#####Precisão
	Este parâmetro indica o maior erro RMS possível dentro da medição. O desvio para a solução single é normalmente de vários metros, com a solução float você pode esperar precisão submétrica, com a solução fix você pode obter precisão de nível centimétrico.

	#####DOP
	DOP significa “diluição da precisão” e especifica o efeito da geometria do satélite na precisão da medição. Quanto melhor a geometria, menor o valor de DOP. O valor padrão para coleta automática é 2, quando o DOP é mais alto, não é recomendado coletar pontos, pois a má geometria dos satélites pode afetar a precisão.

* Se você não quer coletar pontos automaticamente, clique em **"Done"** (Pronto) para continuar. Nesse caso, você precisará iniciar e interromper a coleta de pontos manualmente.

<p style="text-align:center" ><img src="../img/reachview/survey/step2-auto-save-rules.gif" style="width: 800px;" /></p>


####Interface do projeto

A interface do projeto mostra o mapa com a base e o rover. 

* **B** representa a base
* **R** representa o rover

<p style="text-align:center" ><img src="../img/reachview/survey/map-rover-icon.gif" style="width: 800px;" /></p>

####Configuração da altura da antena

* Pressione <img src="../img/reachview/survey/antenna-height-icon.png" align="center" /> para abrir o menu de configuração da altura da antena
* Se você usa o adaptador de rosca 5/8, marque a caixa

!!! note ""
	Reach RS2 possui o padrão de rosca 5/8" e não precisa de adaptador
	
* Altere a altura do bastão se ela for diferente do valor padrão de 2m
* Pressione o botão **"Save"** (Salvar)

<p style="text-align:center" ><img src="../img/reachview/survey/antenna-height.gif" style="width: 800px;" /></p>

####Coletando pontos

* Pressione <img src="../img/reachview/survey/new-point-icon.png" align="center" /> para ir para a próxima janela
	
	Você pode definir o nome do ponto ou usar o padrão. Se você deixar o campo do nome em branco, o nome padrão será “Point 1”, “Point 2”, etc.

	!!! note ""
    	Você tembém pode definir o novo valor da altura do bastão caso ele tenha mudado.

* Pressione **"Collect"** (Coletar) para iniciar o processo de coleta do ponto

<p style="text-align:center" ><img src="../img/reachview/survey/start-point-collecting.gif" style="width: 800px;" /></p>

Se você definiu para coletar pontos automaticamente, verá a barra de status indicando o tempo até o final da coleta dos pontos. Caso contrário, você precisa interromper a coleta do ponto pressionando o botão **"Accept"** (Aceitar).

!!! danger ""
    Se o botão **"Collect"** (Coletar) não estiver disponível e você ver a mensagem “Waiting for solution status” (Aguardando por status da solução), não será possível iniciar a coleta do ponto. Verifique o status da solução.

Você pode interromper o processo pressionando o botão **"Cancel"** (Cancelar). Nesse caso, o ponto não será salvo.

* Se você quiser terminar o levantamento ou olhar para o resultado, pressione o botão **"Back"** (Voltar).
Você verá o mapa com todos os pontos que você coletou

<p style="text-align:center" ><img src="../img/reachview/survey/back-button.gif" style="width: 800px;" /></p>

####Lista de pontos

Para abrir a lista de todos os ontos, pressione <img src="../img/reachview/survey/points-list-icon.png" align="center" />. Você pode abrir os detalhes do ponto, editar as informações do ponto, localizá-lo no mapa ou implantar o ponto.
[Leia mais sobre a função Locação no nosso guia](#locacao-de-pontos).

<p style="text-align:center" ><img src="../img/reachview/survey/list-all-points.gif" style="width: 800px;" /></p>

Além disso, você pode trabalhar com cada ponto separadamente, escolhendo-o no mapa. 

<p style="text-align:center" ><img src="../img/reachview/survey/point-options.gif" style="width: 800px;" /></p>

Quando quiser pausar ou terminar o levantamento, pressione <img src="../img/reachview/survey/back-button-icon.png" align="center" /> para fechar e salvar o projeto. Ele estará disponível no menu da guia Survey.

<p style="text-align:center" ><img src="../img/reachview/survey/close-project.gif" style="width: 800px;" /></p>

####Exportando dados

Quando você terminar a coleta dos pontos, poderá exportar o seu projeto nos formatos CSV, DXF, GeoJSON, DroneDeploy CSV ou ESRI Shapefiles.

Para isso, pressione "•••", clique em **"Export"** (Exportar) e escolha o formato desejado. O download será iniciado automaticamente. Grandes projetos podem levar algum tempo para serem exportados. Depois disso, você pode encontrar o seu arquivo na apsta de downloads padrão.

!!! note ""
	Se você usar o aplicativo ReachView no Android, a exportação será feita em uma pasta de downloads. Quanto ao iOS, você precisa escolher o jeito que deseja salvar seu projeto.

<p style="text-align:center" ><img src="../img/reachview/survey/export-button.gif" style="width: 800px;" /></p>

Também é possível exportar seu projeto na guia Survey sem abri-lo. Clique no botão **"Export"** (Exportar) na janela do projeto e escolha o formato de exportação da mesma maneira explicada anteriormente.

## Locação de pontos

A locação de pontos é um recurso que permite localizar pontos com coordenadas conhecidas.

### Preparando os dados

Abra a guia Survey no ReachView.

<p style="text-align:center" ><img src="../img/reachview/survey/survey.png" style="width: 800px;" /></p>

* Se houver um projeto pronto, clique no nome do projeto para abri-lo

* Se você não tiver nenhum projeto ou quiser criar um novo, [veja a seção Criando um novo projeto deste artigo](#criando-um-novo-projeto)

Você pode usar as coordenadas coletadas anteriormente ou apenas fazer a importação de uma lista com os pontos conhecidos.

#### Importando pontos

Clique no botão "•••" no lado direito do nome do projeto e escolha **"Import"** (Importar) na lista.

<p style="text-align:center" ><img src="../img/reachview/survey/import-points-1.gif" style="width: 800px;" /></p>

Você pode importar arquivos nos formatos CSV, GeoJSON ou DXF ou apenas inserir coordenadas manualmente. 

!!! note ""
	Verifique os modelos para descobrir exatamente como seus dados devem ser.

	??? note "Modelo CSV"
		    name,longitude,latitude,elevation
		    Point 1,30.339,59.958,53.618
		    Point 2,30.334,59.960,58.944

	??? note "Modelo GeoJSON"
		    {
		      "type": "FeatureCollection",
		      "crs": {
		        "type": "name",
		          "properties": {
		            "name": "urn:ogc:def:crs:OGC:1.3:CRS84"
		          }
		       },
		      "features": [
		        {
		          "type": "Feature",
		          "properties": {
		            "name": "Point 1"
		          },
		          "geometry": {
		            "type": "Point",
		            "coordinates": [ 30.339, 59.958, 53.618 ]
		          }
		        },
		        {
		          "type": "Feature",
		          "properties": {
		            "name": "Point 2"
		          },
		          "geometry": {
		            "type": "Point",
		            "coordinates": [ 30.334, 59.960, 58.944 ]
		          }
		        }
		      ]
		    }

Depois de terminar de adicionar as coordenadas, pressione o botão **Import**.

<p style="text-align:center" ><img src="../img/reachview/survey/import-points-2.gif" style="width: 800px;" /></p>

### Interface

Selecione o ponto que você deseja locar. Será destacado em azul. Na parte inferiror da tela, você verá a descrição do ponto que inclui o nome do ponto, a data e a hora UTC da coleta dos pontos e o status da solução.

Clique no botão **"Stakeout"** (Locar) para começar a locação do ponto.

<p style="text-align:center" ><img src="../img/reachview/survey/start-stakeout.gif" style="width: 800px;" /></p>

Vamos verificar interface de locação antes de prosseguir.

<p style="text-align:center" ><img src="../img/reachview/survey/stakeout-interface.PNG" style="width: 800px;" /></p>

* Você pode ver [Status da solução](../../reachview/status/#solution-status), [Relação AR](../../reachview/status/#ar-validation-ratio), [Latência](../../reachview/status/#age-of-differential), número de satélites e [Nome do Reach](../../reachview/settings/#change-reach-name) na barra de status colocada no topo da página. Verifique se você está com solução Fix
* **O valor da altura da antena** pode ser encontrado na barra de status
* Neste modo, o mapa é sempre **Orientado para o norte**
* Há um campo cinza escuro na parte inferior da janela. O valor da esquerda é a  **distância horizontal** até o ponto, o valor correto é **vertical**
* Para terminar a locação do ponto pressione **"Done"** (Pronto)
* Se existir para locar pode alternar usando as setas

### Locando pontos

Tente se mover na direção do ponto. O mapa aumenta automaticamente. 

!!! tip "Como entender qual a direção certa do ponto?"
	Quando começar a andar, você verá o símbolo do Rover mudar para uma seta.

Quando a distância até o ponto for menor que 50 centímetros, o modo de locação muda.

Você precisa colocar o círculo rover azul no anel branco movendo o bastão. Certifique-se de que o bastão não esteja inclinada. O círculo do rover se torna verde? Bom trabalho! Estamos quase terminando.

<p style="text-align:center" ><img src="../img/reachview/survey/stakeout-process.gif" style="width: 800px;" /></p>

Aqui você também pode escolher as opções **2D** ou **3D**. **2D** significa que a locação está considerando somente as coordenadas latitude e longitude. Com o **3D** você também pode encontrar a altura do ponto.

<p style="text-align:center" ><img src="../img/reachview/survey/2D-3D.gif" style="width: 800px;" /></p>

Parabéns! Você acabou de locar o seu primeiro ponto! Agora você pode alternar para outro ponto para continuar ou clicar no botão **"Done"** (Pronto) para concluir.

## A fazer

A ferramenta Survey está melhorando constantemente. Muitos recursos, incluindo novos formatos de exportação, novas configurações de projeto estão chegando em breve. A discussão, incluindo perguntas e solicitação de recursos, está disponível no [fórum da comunidade emlid](https://community.emlid.com).
