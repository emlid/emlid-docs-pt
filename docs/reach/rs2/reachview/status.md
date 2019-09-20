Este é o painel principal com todas as informações sobre posição e recepção de satélite.

## Gráfico SNR (Signal to Noise Ratio) dos Satélites

<p style="text-align:center" ><img src="../img/reachview/status/rs2_status.png" style="width: 800px;" /></p>

O posicionamento RTK requer excelente recepção de sinais dos satélites GNSS. O SNR que é uma relação sinal/ruído é o principal indicador de quão boa é a recepção. O gráfico lista todos os satélites na tela com o seu respectivo SNR. Os dados são atualizados em tempo real.

| Legenda |                   |
|---------|-------------------|
|   R     | Satélites Glonass |
|   G     | Satélites GPS     |
|   E     | Satélites Galileo |
|   J     | Satélites QZSS    |
|   C     | Satélites Beidou  |
 

Quando o SNR de um satélite tiver mais de 45, ele será marcado em verde. Barras cinza indicam SNR da estação base. Vodê deve procurar obter o maior número possível de sinais de satélites na "zona verde". Isso tornará suas medições precisas e a resolução da ambiguidade (Fix) rápida. No topo da tabela SNR, você pode ver indicadores de número de satélites visíveis para receptores móveis e base.

## RTK parameters (Parâmetros RTK)

<p style="text-align:center" ><img src="../img/reachview/status/rs2_rtk_parameters.PNG" style="width: 550px;" /></p>

### Age of differential (Latência)
No caso de um fluxo de correção constante, a age of differential indicará a latência do link. É calculada subtraindo a hora em que a mensagem de correção foi gerada a partir da hora atual do receptor. É uma ferramenta inestimável para debug com problemas de conectividade.

### Baseline (Linha de base)
A linha de base é a distância do rover até a base. Deve ser mantido dentro de 60 Km para o Reach RS2. Se aumentar ainda mais, você poderá ter um tempo de correção mais lento e com menor precisão. A precisão é reduzida em 1 mm a cada km da linha de base.
 
## Map (Mapa)
Um mapa é usado para mostrar sua posição atual. A camada do mapa é fornecida pelo OpenStreetMap.

<p style="text-align:center" ><img src="../img/reachview/status/rs2_map.png" style="width: 800px;" /></p>

Recursos disponíveis no mapa:

+ Last point (último ponto): amplia o mapa até o último ponto.
+ Clear map (limpar): exclui todos os pontos atuais no mapa.
+ Hide background (ocultar plano de fundo): remove a camada OSM.
+ Follow (seguir): mantém o foco no último ponto.
+ Selecione o número de pontos para exibir 100, 1000,10000.




| Significado das cores|             |
|----------------------|-------------|
|        Verde         |   RTK Fix   |
|        Amarelo       |   RTK Float |
|        Vermelho      |   Single    |


### Position (Posição)
Latitude e longitude em WGS84, bem como altura elipsoidal são exibidas na guia Status. O formato de exibição da posição pode ser alterado para XYZ ECEF.

<p style="text-align:center" ><img src="../img/reachview/status/rs2_position.png" style="width: 800px;" /></p>

### Solution status (Status da solução)
**"-"** significa que não há informações para o software processar. Não passou tempo suficiente ou a antena não foi colocada corretamente.  

**Single** significa que o rover encontrou uma solução porém sem correções da base. A precisão no modo autônomo é no nível métrico.

**Float** significa que as correções da base estão sendo levadas em consideração e o posicionamento é relativo às coordenadas da base, mas a ambiguidade dos ciclos não foi resolvida. A precisão no modo flutuante é no nível submétrico.  

**Fix** significa que o posicionamento é relativo à base e a ambiguidade de ciclo foi resolvida. A precisão no modo fixo é centimétrica.


