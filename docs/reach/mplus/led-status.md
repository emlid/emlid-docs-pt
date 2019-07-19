!!! note ""
    Funcionalidade de LED está disponível com o ReachView versão 2.7.0 e atualizações mais recentes 

## Indicadores LED do Reach M+

O Reach M+ tem três LEDs, que são usados como indicadores de status para três partes diferentes do sistema:

| Parte do Sitema | Indicador |
|-----------|------|
|Energia|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/orange.png" style="width: 30px;"></div>  |
|Rede|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/blue.png" style="width: 30px;"></div>  |
|Status|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/green.png" style="width: 30px;"></div>  |



### LED de energia

| Descrição | Demo |
|-----------|------|
|Reach M+ desligado |<div style="text-align: center;"><img src="../img/reachm-plus/led-status/grey.png" style="width: 30px;"></div>  |
|Operação normal|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/orange.png" style="width: 30px;"></div>  |


### LED de rede

Durante a inicialização, o Reach M+ entra em um estado de procura de rede no qual ele tentará se conectar a qualquer rede Wi-Fi conhecida que tenha acesso. Isso pode resultar na conexão a uma rede adicionada anteriormente ou na criação de seu prórpio ponto de acesso.

| Descrição | Demo |
|-----------|------|
|Procurando|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/network-scanning-led.gif" style="width: 30px;"></div>  |
|Conecectado a rede Wi-Fi|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/client-led.gif" style="width: 30px;"></div>  |
|Modo ponto de acesso|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/blue.png" style="width: 30px;"></div>  |

O comportamento do Led de rede muda toda vez que você altera o modo Wi-Fi via ReachView. Ele refletirá a ativação do ponto de acesso, a procura por redes Wi-Fi e a conexão a redes sem fio existentes.

### LED de status

O LED de status é usado para exibir o status do ReachView. 

| Descrição | Demo |
|-----------|------|
|Sincronização do relógio|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/time-sync-led.gif" style="width: 30px;"></div>  |
|Operação normal|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/green.png" style="width: 30px;"></div>  |
|Coleta de pontos|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/point-collection-led.gif" style="width: 30px;"></div>  |
|Erro interno|<div style="text-align: center;"><img src="../img/reachm-plus/led-status/grey.png" style="width: 30px;"></div>  |


### Sincronização do relógio
Após a configuração da rede, o LED verde começará a piscar. É mostrado durante a sincronização do relógio.

!!! Alerta ""
    O aplicativo não será iniciado até que a sincronização de tempo seja concluída. A conexão com a internet permite que isso aconteça automaticamente, mas no modo de ponto de acesso, o Reach requer uma antena conectada com alguma visibilidade de satélite.



### Comportamento do LED

A tabela abaixo demonstra possíveis combinações de flash dos LEDs, descrevendo vários status do receptor.  


| Status do Reach M+  |  Demo |
|--------------|-------|
|<br><br><br><br> <div style="text-align: center;">    Desligado   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/off.png" style="height: 150px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Carregando   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/loading.gif" style="height: 150px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Sincronização do relógio   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/time-sync.gif" style="height: 150px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Procurando rede Wi-Fi   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/network-scan.gif" style="height: 150px;"></div> |
|<br><br><br><br> <div style="text-align: center;">     App em execução, modo conectado a uma rede Wi-Fi   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/running-client.gif" style="height: 150px;"></div>
|<br><br><br><br> <div style="text-align: center;">    App em execução, modo ponto de acesso   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/running-hotspot.gif" style="height: 150px;"></div> |
|<br><br><br><br> <div style="text-align: center;">    Ponto coletado <br> _assumindo que o dispositivo está no modo ponto de acesso_   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/point-collection.gif" style="height: 150px;"></div>
|<br><br><br><br> <div style="text-align: center;">    Erro interno <br> _assumindo que o dispositivo está no modo ponto de acesso_   </div>   | <br>  <div style="text-align: center;"><img src="../img/reachm-plus/led-status/error.png" style="height: 150px;"></div>
