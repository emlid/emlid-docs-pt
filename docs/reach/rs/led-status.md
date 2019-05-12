!!! nota ""
    Funcionalidade de LED está disponível com ReachView versão 2.7.0

## Indicadores LED do Reach RS/RS+

Reach RS / RS + tem três LEDs, que são utilizados como indicadores de status para três diferentes partes do sistema:

| Parte do Sistema | Indicador |
|-----------|------|
|Energia|<div style="text-align: center;"><img src="../img/reachrs/led-status/orange.png" style="width: 30px;"></div>  |
|Rede|<div style="text-align: center;"><img src="../img/reachrs/led-status/blue.png" style="width: 30px;"></div>  |
|Stat|<div style="text-align: center;"><img src="../img/reachrs/led-status/green.png" style="width: 30px;"></div>  |



### LED energia e botão de energia

| Descrição | Demo |
|-----------|------|
|Operação normal|<div style="text-align: center;"><img src="../img/reachrs/led-status/orange.png" style="width: 30px;"></div>  |
|Bateria carregando|<div style="text-align: center;"><img src="../img/reachrs/led-status/charge.gif" style="width: 30px;"></div>  |
|Bateria baixa|<div style="text-align: center;"><img src="../img/reachrs/led-status/low-battery.gif" style="width: 30px;"></div>  |

LED de energia também irá confirmar o desligamento (depois de segurar o botão de energia durante três segundos) com três piscadas rápidas.

### LED de rede

Quando o Reach RS/RS+ é iniciado, ele busca por redes conhecidas e tenta conectar-se a elas. Então ele pode-se conectar a uma rede adicionada anteriormente ou entrar no modo ponto de acesso.

| Descrição | Demo |
|-----------|------|
|Procurando|<div style="text-align: center;"><img src="../img/reachrs/led-status/network-scanning-led.gif" style="width: 30px;"></div>  |
|Conectado a rede Wi-Fi|<div style="text-align: center;"><img src="../img/reachrs/led-status/client-led.gif" style="width: 30px;"></div>  |
|Modo ponto de acesso|<div style="text-align: center;"><img src="../img/reachrs/led-status/blue.png" style="width: 30px;"></div>  |

O comportamento do LED de rede muda toda vez que você alterar o modo do Wi-Fi via ReachView. Ele irá virar um ponto de acesso, buscar uma rede e conectar a uma rede Wi-Fi existente.

### LED Stat

LED Stat é usado para exibir o status de ReachView.

| Descrição | Demo |
|-----------|------|
|Sincronização do relógio|<div style="text-align: center;"><img src="../img/reachrs/led-status/time-sync-led.gif" style="width: 30px;"></div>  |
|Operação normal|<div style="text-align: center;"><img src="../img/reachrs/led-status/green.png" style="width: 30px;"></div>  |
|Coleta de ponto|<div style="text-align: center;"><img src="../img/reachrs/led-status/point-collection-led.gif" style="width: 30px;"></div>  |
|Erro interno|<div style="text-align: center;"><img src="../img/reachrs/led-status/grey.png" style="width: 30px;"></div>  |

!!! Atenção ""
    Reach RS/RS+ requer tempo sincronização apenas durante a configuração inicial. Conexão de Internet, que é necessário para primeira inicialização, permitirá que o processo de sincronização de tempo aconteça automaticamente.

### Comportamento do LED

A tabela abaixo demonstra as possibilidades de combinações descrevendo vários status do receptor.


| Estado do Reach  |  Demo |
|--------------|-------|
|<br><br><br><br> <div style="text-align: center;">    Desligado   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/off.png" style="height: 250px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Reach RS+ carregando   </div>   | <br> <div style="text-align: center;"><img src="../img/reachrs/led-status/RS-plus-charging.gif" style="height: 250px;"></div> |
|<br><br><br><br> <div style="text-align: center;">   Reach RS carregando     </div>   | <br> <div style="text-align: center;"><img src="../img/reachrs/led-status/off.png" style="height: 265px;"></div>  |
|<br><br><br><br> <div style="text-align: center;">    Reach RS+ charging after connecting the cable   </div>|<br> <div style="text-align: center;"><img src="../img/reachrs/led-status/RS-plus-charging-after-connecting-the-cable.gif" style="height: 250px;"></div>|
|<br><br><br><br> <div style="text-align: center;">    Reach RS behavior after connecting the cable   </div>|<br> <div style="text-align: center;"><img src="../img/reachrs/led-status/RS-no-reaction.gif" style="height: 250px;"></div>|
|<br><br><br><br> <div style="text-align: center;">    Carregando   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/loading.gif" style="height: 265px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Reach RS+ loading after connecting the cable   </div>|<br> <div style="text-align: center;"><img src="../img/reachrs/led-status/RS-plus-loading-after-connecting-the-cable.gif" style="height: 250px;"></div>|
|<br><br><br><br> <div style="text-align: center;">    Sincronização de tempo   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/time-sync.gif" style="height: 250px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Bateria baixa   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/lack-of-power.gif" style="height: 250px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Procurando de rede   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/network-scan.gif" style="height: 250px;"></div> |
|<br><br><br><br> <div style="text-align: center;">     Conectado a um Wi-Fi   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/running-client.gif" style="height: 250px;"></div>
|<br><br><br><br> <div style="text-align: center;">    Modo ponto de acesso   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/running-hotspot.png" style="height: 250px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Coleta de ponto <br> _assumindo que o dispositivo está em modo ponto de acesso_   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/point-collection.gif" style="height: 250px;"></div>
|<br><br><br><br> <div style="text-align: center;">    Erro interno  <br> _assumindo que o dispositivo está em modo ponto de acesso_   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachrs/led-status/error.png" style="height: 250px;"></div>
