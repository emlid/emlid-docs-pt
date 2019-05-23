Este é o painel principal com todas as informações sobre posição e recepção de satélite.

## Gráfico SNR de satélite

<p style="text-align:center" ><img src="../img/reachview/status/status.png" style="width: 800px;" /></p>

O posicionamento RTK requer excelente recepção de sinais dos satélites GNSS. SNR (Signal to Noise Ratio) é o principal indicador de quão boa é a recepção. O gráfico lista todos os satélites que se encaixam no tamanho da tela e o SNR correspondente. Os dados são atualizados em tempo real.

| Legenda |                   |
|--------|-------------------|
|   R    | Satélite Glonass  |
|   G    | Satélite GPS      |
|   #    | Satélite SBAS     |
|   E    | Satélite Galileo  |
|   J    | Satélite QZSS     |
|   C    | Satélite Beidou   |


Quando o SNR de um satélite estiver acima de 45, ele será marcado em verde. Barras cinza indicam SNR da estação base. Você deve procurar alcançar tantos sinais de satélites na “zona verde” quanto possível. Isso fará com que suas medições sejam precisas e a resolução de ambiguidade (Fix) seja rápida. No topo do gráfico SNR você pode ver indicadores de números de satélites visíveis para receptores rover e base.

## Parâmetros do RTK

<p style="text-align:center" ><img src="../img/reachview/status/rtk_parameters.png" style="width: 550px;" /></p>

### Correção diferencial
No caso de um fluxo de correção constante, a idade do diferencial indicará a latência do link. É calculado subtraindo a hora em que a mensagem de correção foi gerada a partir do tempo atual do receptor. É uma ferramenta inestimável para depurar problemas de conectividade.

### Relação de validação de AR  
Este é o resultado do teste de razão realizado na solução potencial “Fix”, que mostra quantas vezes é a melhor solução melhor do que a próxima. Se esse número for maior que 3, o Reach considerará a solução RTK como Fixo.

### Linha de base
Linha de base é a distância do rover até a base. Ele deve ser mantido dentro de 10 km, se ele for aumentado ainda mais, poderá ocorrer um tempo de correção mais lento e menor precisão. A precisão é diminuída em 1 mm por cada km da linha de base.

## Mapa
Mapa integrado é usado para mostrar sua posição atual. A camada do mapa é fornecida pelo OpenStreetMap.

<p style="text-align:center" ><img src="../img/reachview/status/map.png" style="width: 800px;" /></p>

Recursos disponíveis do mapa:

+	Último ponto: amplia o mapa para o último ponto.
+	Limpar mapa: exclui todos os pontos atuais no mapa.
+	Ocultar plano de fundo: remove a camada OSM.
+	Siga: mantém o foco no último ponto.
+	Selecione o número de pontos para mostrar 100, 1000, 10000.




| Significado de cores pontuais |               |
|-------------------------------|---------------|
|        Verde                  |  Correção RTK |
|        Amarelo                | Flutuante RTK |
|        Vermelho               |   Autônomo    |


### Posição
É exibido a Latitude e Longitude em WGS84, altura elipsoidal na guia de status. O formato de exibição de posição pode ser alterado para XYZ ECEF.

<p style="text-align:center" ><img src="../img/reachview/status/position.png" style="width: 800px;" /></p>

### Estado da solução
**"-"** significa que não há informações para o software processar. Não passou tempo suficiente ou a antena não está colocada corretamente.  

**Autônomo** significa que o rover encontrou uma solução que depende de seu próprio receptor e não há correções de nenhuma base. Configurar o modo de posicionamento para Autônomo também resultará nesse status. A precisão no modo autônomo é métrica.

**Flutuante** significa que as correções base agora são levadas em consideração e o posicionamento é relativo às coordenadas de base, mas a ambiguidade não está resolvida. A precisão no modo de flutuante é sub-métrica.

**Fixo** significa que o posicionamento é relativo à base e a ambiguidade está resolvida. A precisão no modo fixo é centimétrica.
