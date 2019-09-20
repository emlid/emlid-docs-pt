# RTK settings (Configurações RTK)

## RTK options (Opções RTK)

<p style="text-align:center" ><img src="../img/reachview/rtk-settings/rtk-settings-rs2.png" style="width: 800px;" /></p>

### Positioning mode (Modo de posicionamento)

+ **Kinematic (Cinemático)** - modo de posicionamento mais usado, assume-se que o receptor está se movendo
+ **Static (Estático)** - assume-se que o Reach está estático. Restringir o sistema ajuda a resolver ambiguidades mais rapidamente, além de produzir medições com maior precisão

### Elevation mask angle (Ângulo da máscara de elevação)
Os satélites abaixo da elevação definida serão excluídos do cálculo. A configuração padrão é 15 graus. Geralmente, os satélites com altitude mais baixa fornecem medições muito ruidosas.

### SNR mask (Máscara SNR)
Os satélites com baixo SNR serão excluídos do cálculo. A configuração padrão é 35.

## GNSS selection (Seleção GNSS)

O Reach RS2 rastreia os sistemas de satélites GPS, GLONASS, GALILEO, QZSS, e BEIDOU. Os dados podem ser registrados com taxa de atualização de 1 Hz, 5 Hz ou 10 Hz.

Todos GNSS ativado em 5 Hz é nossa recomendação padrão.
