## Visão geral

A técnica cinemática em tempo real requer dois receptores. Um deles é estacionário e é chamado de “estação base”, o outro é “rover”. A estação base mede os erros e, sabendo que está parada, transmite correções ao rover (consult [Como funciona o RTK](../../tutorials/rtk-introduction) para obter mais informações sobre o RTK). Às vezes, as redes CORS e NTRIP ocupam o lugar das estações base tradicionais. Eles fornecem uma posição absoluta precisa e enviam correções pela Internet. Normalmente, a distância entre a estação de referência e o rover local não deve exceder 10 a 15 km, devido ao efeito ionosférico. Portanto, se a estação de referência estiver localizada longe demais ou simplesmente estiver ausente na área, você precisará de uma estação base local. Outras vantagens da sua própria base são a independência da conexão com a Internet e a isenção de taxas de assinatura NTRIP.

Se você está configurando sua própria base, é importante prestar atenção a este artigo. Um bom entendimento das diferentes maneiras de configurar a base ajudará você a alcançar a precisão desejada para sua aplicação.


## Posição absoluta e relativa
O ReachView tem várias maneiras de determinar ou definir a posição da estação base, fornecendo vários níveis de precisão. Vamos dar uma olhada na figura abaixo (figura 1). O algoritmo RTK calcula com precisão a distância entre a base e o rover. Essa distância é chamada de linha de base. A posição do Rover é precisamente determinada em relação à posição da Base. Ao mesmo tempo, o deslocamento das coordenadas do rover a partir da localização real depende da precisão da posição da base. Se a posição que foi definida na estação base for diferente da posição real na Terra, o deslocamento igual a essa diferença também estará na posição móvel.

<p style="text-align:center"><img src="../img/reach/placing-the-base/position.png" style="width: 800px;"/></p>
_Figura  1_  
<br>
Geralmente, é suficiente saber a posição precisa de um objeto relativamente à estação de base, mas para algumas aplicações, como levantamento e mapeamento, é fundamental obter uma posição absoluta precisa. Neste caso, o desvio ΔX, ΔY, ΔZ entre a posição real e a posição da estação base deve ser evitado ou reduzido.
<br>

!!! Atenção ""
    A posição absoluta do rover é precisa na mesma proporção da base.

O posicionamento adequado da estação base é a chave para uma coleta de dados bem-sucedida. O deslocamento das coordenadas de base manterá os dados coletados precisos, mas não acurados (o que é absolutamente adequado para medições volumétricas, mas é inaceitável se você tiver que vincular os dados coletados às coordenadas globais). Por exemplo, se você estiver processando o mapa usando dados coletados por drone equipado com RTK usando correções da base deslocada, seu mapa será georreferenciado posteriormente com o mesmo deslocamento (figura 2).

<p style="text-align:center"><img src="../img/reach/placing-the-base/absolute-shift.png" style="width: 800px;"/></p>
_Figura 2_  
<br>
O mesmo efeito de produção de turno pode ser observado se a base for colocada de forma incorreta sobre um ponto conhecido ou apenas movida de sua posição determinada sem alterações relevantes.

!!! Nota útil
    Se a posição absoluta precisa da base tiver sido determinada somente após o trabalho ter sido feito, o deslocamento do mapa pode ser determinado e corrigido.


## Maneiras de definir a base

Como já mencionado, Reach e Reach RS/RS+ usados como base podem ser posicionados de várias maneiras. Você pode inserir manualmente as coordenadas de base, usar o recurso de média ou usar as técnicas de PPP e PPK para determinar as coordenadas.

| Método de configuração base         | Precisão        | Necessário                   | Tempo de observação | Tempo de processamento                                                             | Custo                                |
|---------------------------|-----------------|-------------------------------|------------------|------------------------------------------------------------------------------|-------------------------------------|
| Manual, em um ponto conhecido  | mesmo que o ponto | Ponto conhecido                   | 0 min            | Imediato, nenhum processamento é necessário                                            | Livre                                |
| Média de posição autônoma (single)  | ~2.5 m           |                               | &lt;5 min            | Imediato, processando no Reach                                               | Livre                                |
| Posição RTK FIX          | 7mm+1mm/km      | Conexão NTRIP da base <15km  | &lt;5 min            | Imediato, processando no Reach                                               | Grátis / $$ dependendo do provedor local |
| Posição flutuante RTK        | 1.0m            | Conexão NTRIP da base <100km | &lt;15 min           | Imediato, processando no Reach                                               | Grátis / $$ dependendo do provedor local |
| Pós-processado cinemático  | 7mm+1mm/km      | Logs RINEX da base <100km   | ~1 h              | 15min no PC após o log da estação de referência disponível, geralmente postado de hora em hora | Grátis / $ dependendo do provedor local  |
| Posicionamento preciso de pontos | ~30cm           |                               | ~4 h              | Em ~ 24h após o envio de logs para o serviço online da NRCan ou IBGE                        | Livre                                |

_Os números na tabela são aproximados e apenas para fins de referência. Sua experiência pode variar em diferentes condições, sempre siga as práticas de Criando Novo Projeto adequadas!_

<br>

Não importa qual método você use a posição relativa do rover sempre terá precisão centimétrica, a precisão real será definida pela precisão da posição base.

!!! Dica ""
    Consulte a [aba Modo base do tutorial do ReachView](../../reachview/base-mode/#base-position) para aprender várias maneiras de como configurar a base com o ReachView.

#####MANUAL
A entrada manual da posição é bastante direta e é usada quando você tem acesso a um ponto conhecido. Os cenários mais populares incluem encontrar um ponto trigonométrico ou contratar um topógrafo que irá definir o ponto de referência. Neste caso, a precisão absoluta depende da precisão com que as coordenadas do ponto foram determinadas.
<p style="text-align:center"><img src="../img/reach/placing-the-base/trig.jpg" style="width: 800px;"/></p>
_Estação de triangulação também conhecida como ponto trigonométrico ou farol trigonométrico com o Reach RS/RS+ no topo (foto de Luke Wijnberg)_
<br>

Preste atenção e coloque cuidadosamente a base sobre um ponto conhecido e meça a altura da antena a partir da marca. Isso ajudará a evitar mudanças da posição absoluta e manterá as medições precisas. Consulte [Montando o Reach RS/RS + no campo](#placing-the-base-station-in-the-field) para obter instruções detalhadas.

#####MÉDIA
Vamos dar uma olhada mais de perto na configuração da base usando a média da posição com soluções autônomas (single), flutuantes ou fixas. Todas essas maneiras fornecem diferentes níveis de precisão de coordenadas de base e são adequadas para diferentes aplicações.

####MÉDIA AUTÔNOMA(single)
Essa abordagem é usada quando você não requer precisão absoluta. A média acontece no modo de GPS autônomo sem usar nenhuma correção e isso fornece uma precisão absoluta de vários metros.

A ilustração à esquerda abaixo (veja a figura 3) mostra os caminhos do rover que faz um contorno de um retângulo várias vezes. Este rover recebe as correções da base configurada usando uma solução única média. Se for obtida uma nova coordenada média autônoma para a base, sem trocar o receptor de lugar, a posição absoluta será diferente em alguns metros. Podemos ver isto se for repetido o processo de média autônoma da base e refazer imediatamente o mesmo retângulo. Dê uma olhada à direita da figura 3.


<p style="text-align:center"><img src="../img/reach/placing-the-base/averaged-single.png" style="width: 800px;"/></p>
_Figura 3_  
<br>

!!! tip "Perfeito para o posicionamento relativo preciso e repetitivo (orientação do trator GPS, voos autônomos e pouso)"
    Se você precisar apenas de posicionamento relativo preciso, a maneira mais fácil é calcular a média da posição usando uma única solução. Apenas marque fisicamente o ponto no chão e salve as coordenadas para manual no ReachView. O resultado do dia-a-dia seria quase idêntico àqueles obtidos usando correções NTRIP.

#### Média de fixo e float

A solução média de correção RTK é muito mais precisa do que a média autônoma (single) e é possível quando o receptor usado como base é configurado para obter correções NTRIP pela Internet. Isso pode ser útil se a estação de referência estiver localizada longe. Reduzir a linha de base instalando a base local melhora o desempenho de posicionamento do rover.

<p style="text-align:center"><img src="../img/reach/placing-the-base/averaged-float.gif" style="width: 600px;"/></p>

À esquerda da próxima ilustração (veja a figura 4), o rover passa várias vezes o contorno retangular marcado. Este rover recebe as correções da base configurada usando a posição média fixa.
Quando a base é configurada usando a solução média fixa, as coordenadas são determinadas com precisão centimétrica (se forem obtidas correções NTRIP). Neste caso, os desvios de cada caminho construídos imediatamente após a reavaliação várias vezes estarão dentro de poucos centímetros. Dê uma olhada à direita da figura 4.

<p style="text-align:center"><img src="../img/reach/placing-the-base/averaged-fix.png" style="width: 800px;"/></p>
_Figura 4_  
<br>

Se a linha de base for muito longa para obter correção, calcular a média da solução flutuante ainda melhorará a posição para um nível de ~ 1m.

!!! tip "Perfeito para coleta e levantamento de dados, colocando GCPs e mapeamento de drones"
    A média da posição base usando a solução fixa fornece centímetros de precisão e funciona muito bem quando você precisa de uma posição absoluta precisa!


#### Cinemática pós-processada
Com a técnica de cinemática pós-processada, você pode determinar coordenadas de base sem correções em tempo real com precisão centimétrica. Você precisará de registros RINEX da estação de referência na área de 100 km e do registro de dados brutos do receptor. O processo levará cerca de 15 minutos para calcular a posição da sua estação base usando [o tutorial PPK dos documentos.](../../tutorials/gps-post-processing)

Etapas gerais:

* Ativar o [registro de dados brutos](../../reachview/logging/) e registro de registro por cerca de uma hora
* Exportar log com os dados coletados do ReachView para o seu PC
* Consulte o [PPK tutorial](../../tutorials/gps-post-processing)
* Depois de obter as coordenadas, você poderá inseri-las manualmente na seção Coordenadas da base. **Comparar a posição PPK com a posição média e aplicar correções aos dados coletados é a maneira de compensar o deslocamento mostrado no exemplo da figura 2.**

#### Posicionamento por Ponto Preciso

Com a técnica de posicionamento de ponto preciso, você pode determinar com precisão as coordenadas de base em qualquer parte do mundo sem correção em tempo real ou estação de base nas proximidades, no entanto, pode levar um tempo considerável para obter coordenadas.

Etapas gerais:

* Ativar o [registro de dados brutos](../../reachview/logging/) e registrar registros por algumas horas
* Exportar log com os dados coletados do ReachView para o seu dispositivo móvel ou PC
* Carregar o arquivo coletado para o serviço PPP (por exemplo, [NRCAN](https://webapp.geod.nrcan.gc.ca/geod/tools-outils/ppp.php))
* Depois de obter as coordenadas, você poderá inseri-las manualmente na seção Coordenadas básicas.


### Colocando a estação base no campo

!!! danger "Preste atenção!"
    A medida incorreta da altura da antena é provavelmente o erro mais frequente no levantamento de pontos com GPS.

#### Montando o Reach RS/RS+ (Figura 5)

* Certifique-se de que o seu dispositivo Reach está colocado precisamente acima do ponto marcado no tripé e nivelado
*	Se você estiver configurando coordenadas de base, meça manualmente o deslocamento da altura da antena


!!! note ""
    A altura da antena é medida como a distância entre o marco e o ponto de referência da antena (ARP).

 Para o Reach RS/RS+, considere a altura da antena como a distância entre o marco e a parte inferior do Reach RS/RS+ (h na figura 5) mais 65 mm.

<p style="text-align:center"><img src="../img/reach/placing-the-base/placing-reach-rs.png" style="width: 800px;"/></p>  
_Figura 5_
 <br>

*	Quando você posicionou o Reach RS/RS+ com segurança sobre a marca, você está pronto para definir ou determinar sua posição.

#### Montando o Reach (Figura 6)

* Coloque a antena Tallysman no plano de aterramento, conforme descrito na [seção Montagem da antena do Reach](https://docs.emlid.com/reach/antenna-placement/#ground-plane).
* Certifique-se de que a antena Reach está posicionada precisamente acima do ponto marcado no tripé e nivelada
* Se você estiver configurando coordenadas de base, meça manualmente o deslocamento da altura da antena. Para antena Tallysman indo com Reach, ARP é a superfície inferior.
<p style="text-align:center"><img src="../img/reach/placing-the-base/placing-reach.png" style="width: 800px;"/></p>  
_Figura 6_
 <br>

* Quando você posicionou a antena do Reach com segurança sobre a marca, você está pronto para definir ou determinar sua posição.


### Armazenando a posição base

Se você quiser reutilizar o determinado local de base:

* Marcar com cuidado a posição física no chão
* Salvar coordenadas para inserção manual de coordenadas da base na aba Modo Base (Base mode)
* Ao utilizar esta posição na próxima vez, posicione a estação base com precisão sobre a marca
* Insira as coordenadas gravadas manualmente no ReachView
