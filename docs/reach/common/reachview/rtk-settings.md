## Opções do RTK

<p style="text-align:center" ><img src="../img/reachview/rtk_settings/rtk_set.png" style="width: 800px;" /></p>

### Positioning mode

+	**Single (Autonomo)** – modo de posicionamento sem fonte de correção.
+	**Kinematic (Cinemático)** – modo mais utilizado de posicionamento, pressupõe que o receptor está se movendo.
+	**Static (Estático)** –  supõe-se que o Reach está estático. Restringi o sistema a ajudar resolver ambiguidades mais rápido, entretanto as medições possuem melhor precisão.


### AR mode
Existem duas estratégias principais para a resolução de ambiguidades:

+ **Fix-and-hold (Corrigir e manter)**: após a primeira ambiguidade fixa (resolvida), força mantê-la. Fixo é mais estável, mas no caso da primeira inicialização não ser correta levará mais tempo para recuperar e inicializar corretamente. Você pode pensar nisso como se o Fixo tivesse inércia.
+ **Continuous (Contínuo)**: ambiguidades são resolvidas, época por época. Menos estável, mas sem risco de manter uma falsa correção.

Em condições reais sobre uma plataforma em movimento, Fix-and-hold (Corrigir e manter) fornece melhor desempenho geral.

### Glonass AR mode
Ao contrário do GPS, todos os satélites GLONASS transmitem em frequências diferentes, o que resulta em Inter Channel Biases (ICB) que são exclusivos para cada modelo de receptor.
Reach pode corrigir o ICB do GLONASS, permitindo ativar o GLONASS AR com bases que não sejam Reach, como casters NTRIP. A recomendação geral é para manter GLONASS AR sempre ligado (on).

### Elevation mask angle
Satélites mais baixos que elevação definida serão excluídos do cálculo. A configuração padrão é 15 graus. Geralmente os satélites com menor elevação fornecem dados com muitos ruídos.

### SNR mask
Satélites com SNR baixo serão excluídos do cálculo. Configuração padrão é 35.

### Max acceleration
Configure de acordo com suas experiências de aceleração da sua plataforma. Se você não tiver certeza sobre o valor correto recorra ao catálogo e use RTKPLOT para ver que tipo de acelerações estão presentes na sua aplicação. O valor padrão é 1 m/s^2.

## GNSS Selection

<p style="text-align:center" ><img src="../img/reachview/rtk_settings/gnss_sel.png" style="width: 800px;" /></p>

Dependendo da sua localização pode ser benéfico escolher certo conjunto de sistemas GNSS:

+ GPS + Glonass + SBAS + QZSS a 5 Hz é nossa recomendação padrão.
+ GPS + Beidou + SBAS + QZSS a 5 Hz recomendado para APAC, onde QZSS e Beidou é visível.
+ GPS + SBAS + QZSS a 14 Hz para plataformas mais dinâmicas que exigem atualização alta taxa.

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
