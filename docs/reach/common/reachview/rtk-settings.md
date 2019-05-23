## Opções RTK

<p style="text-align:center" ><img src="../img/reachview/rtk_settings/rtk_set.png" style="width: 800px;" /></p>

### Modo de posicionamento

+	Single – modo de posicionamento sem fonte de correção.
+	Cinemática – modo mais utilizado de posicionamento, pressupõe que o receptor está se movendo.
+	Estática –  uma suposição é feita que o Reach é estático. Restringi o sistema a ajudar resolver ambiguidades mais rápido, bem como produzir medições com maior precisão.


### AR (Resolução de Ambiguidade) mode
Existem duas estratégias principais para a resolução de ambiguidades:

+ Corrigir e manter: após a primeira ambiguidade fixa (resolvida), forcar mantê-la. Fixo é mais estável, mas no caso da primeira inicialização não ser correta levará mais tempo para recuperar e inicializar corretamente. Você pode pensar nisso como se o Fixo tivesse inércia.
+	Contínuo: ambiguidades são resolvidas, época por época. Menos estável, mas sem risco de manter uma falsa correção.

Em condições reais sobre uma plataforma em movimento, Corrigir e manter fornece melhor desempenho geral.

### Glonass AR mode
Ao contrário do GPS, todos os satélites GLONASS transmitem em frequências diferentes, o que resulta em Inter Channel Biases (ICB) que são exclusivos para cada modelo de receptor. Ao usar a estação base que não seja Reach ou Reach RS/RS+ você deve desativar a resolução de ambiguidade Glonass ou calibrá-lo. Os ICBs podem ser calibrados utilizando satélites GPS, se você definir o GLONASS AR para Corrigir e manter. Neste modo de resolução de ambiguidade inicial será executada usando GPS e de acordo com o resultado ICBs GLONASS será calculado e usado mais tarde no posicionamento.

### Ângulo da máscara de elevação
- •	Satélites mais baixos que elevação definida, serão cálculo. Configuração padrão é 15 graus. Geralmente os satélites com menor elevação fornecem dados com muitos ruídos.

### Máscara SNR
- •	Satélites com SNR baixo serão excluídos do cálculo. Configuração padrão é 35.

### Máxima aceleração
- Configure de acordo com suas experiências de aceleração da sua plataforma. Se você não tiver certeza sobre o valor correto recorra ao catálogo e use RTKPLOT para ver que tipo de acelerações estão presentes na sua aplicação. O valor padrão é 1 m/s^2.

## Seleção GNSS

<p style="text-align:center" ><img src="../img/reachview/rtk_settings/gnss_sel.png" style="width: 800px;" /></p>

Dependendo da sua localização pode ser benéfico escolher certo conjunto de sistemas GNSS:

+ GPS + Glonass + SBAS + QZSS a 5 Hz é nossa recomendação padrão.
+	GPS + Beidou + SBAS + QZSS a 5 Hz recomendado para APAC, onde QZSS e Beidou é visível.
+	GPS + SBAS + QZSS a 14 Hz para plataformas mais dinâmicas que exigem atualização alta taxa.

### Seleção de GNSS de acordo com o registro
Recomendamos usar as seguintes configurações para voos PPK:

| Sistema                               | Frequência |
|---------------------------------------|-----------|
| GPS + GLONASS + GALILEO + SBAS + QZSS | 1 Hz      |
| GPS + GLONASS + QZSS                  | 5 Hz      |
| GPS + GALILEO                         | 5 Hz      |
| GPS                                   | 10 Hz     |


!!! danger "Atenção"
    Use uma das configurações acima estáveis para evitar perder registro de arquivos.
