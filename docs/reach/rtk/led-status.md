!!! tip ""
	O Reach foi substituído por [Reach M+](https://emlid.com/reach). A documentação do Reach M+ pode ser encontrada [aqui](https://docs.emlid.com/reachm-plus/).


!!! note ""
    Funcionalidade de LED está disponível com o ReachView versão 2.7.0 e mais recente 


## Sequência do LED de inicialização do Reach

O LED do Reach é um LED RGB que percorre um padrão simples:

Estado da rede -> estado do aplicativo

Durante o boot, o Reach passará por três etapas:

* Varredura de rede
* Sincronização de tempo
* Acesso ao ReachView

### Varredura de rede

Durante a inicialização, o Reach entre em um estado de varredura de rede no qual ele tentará se conectar a qualquer rede Wi-Fi conhecida que possa encontrar. Isso pode resultar no conexão a uma rede adicionada anteriormente ou no criação de seu próprio ponto de acesso.

| Descrição | Demo |
|-----------|------|
|Procurando|<div style="text-align: center;"><img src="../img/reach/led-status/network-scanning-led.gif" style="width: 30px;"></div>  |
|Conectado a rede Wi-Fi|<div style="text-align: center;"><img src="../img/reach/led-status/blue.png" style="width: 30px;"></div>  |
|Modo ponto de acesso|<div style="text-align: center;"><img src="../img/reach/led-status/white.png" style="width: 30px;"></div>  |


### Sincronização de tempo

Após a configuração, **<font color="magenta">magenta</font> piscará** e será adicionada ao LED. Eles são mostrados durante a sincronização de tempo.

!!! danger ""
    O aplicativo não será iniciado até que a sincronização de tempo seja concluída. A conexão com a internet permite que isso aconteça automaticamente, mas no modo de ponto de acesso, o Reach requer uma antena conectada com alguma visibilidade de satélite.

### Acesso e operação do ReachView

Após a sincronização de tempo, o **piscar magenta** parará e o ReachView será iniciado. Entrará a **<font color="luz verde">Green</font> sólido** em seu lugar, mostrando o inicío do aplicativo. Você pode ver vários status adicionais:

| Status do LED | Demo |
|-----------|------|
|Operação normal do Aplicativo|<div style="text-align: center;"><img src="../img/reach/led-status/green.png" style="width: 30px;"></div>  |
|Coletando pontos|<div style="text-align: center;"><img src="../img/reach/led-status/point-collection-led.gif" style="width: 30px;"></div>  |
|Erro interno do aplicativo|<div style="text-align: center;"><img src="../img/reach/led-status/red.png" style="width: 30px;"></div>  |


### Comportamento do LED

A tabela abaixo demonstra possíveis padrões de flash descrevendo vários status do recptor.  


| Statu do Reach | Sincronização de tempo   -> | Rede   -> | Status do aplicativo | Demo |
|--------------|-----------|---------------------|---------|-----------|
|<br> <div style="text-align: center;">    Desligado   </div>                   | <br>  </div>    |  <br> </div> | <br> </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/off.png" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Falta de energia   </div>                   | <br>  <div style="text-align: center;"><img src="../img/reach/led-status/magenta.png" style="height: 30px;"><br>Pisca a cada 10-15 seg</div>    |  <br> </div> | <br> </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/low-power.gif" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Procurando rede   </div>                   | <br>  </div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/blue.png" style="height: 30px;"><br>Pisca rápido</div> | <br> </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/network-scan.gif" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Sincronização de tempo no modo Wi-Fi   </div>                   | <br>  <div style="text-align: center;"><img src="../img/reach/led-status/magenta.png" style="height: 30px;"><br>Solido</div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/blue.png" style="width: 30px;"><br>Solido</div> | <br> </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/time-sync-client.gif" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Sincronização de tempo no modo ponto de acesso, <br> _a visibilidade de satélites é necessária_   </div>                   | <br>  <div style="text-align: center;"><img src="../img/reach/led-status/magenta.png" style="height: 30px;"><br>Solido</div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/white.png" style="width: 30px;"><br>Solido</div> | <br> </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/time-sync-hotspot.gif" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Aplicativo em execução,<br> Modo Wi-Fi   </div>                   | <br>  </div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/blue.png" style="height: 30px;"><br>Solid</div> | <br><div style="text-align: center;"><img src="../img/reach/led-status/green.png" style="height: 30px;"><br>Solido </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/running-client.gif" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Aplicativo em execução, <br>Modo ponto de acesso    </div>                   | <br>  </div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/white.png" style="height: 30px;"><br>Solido</div> | <br><div style="text-align: center;"><img src="../img/reach/led-status/green.png" style="height: 30px;"><br>Solido </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/running-hotspot.gif" style="width: 150px;"></div>   | 
|<br> <div style="text-align: center;"> Coletando pontos, <br> _assumindo que o Reach está_ <br> _no modo ponto de acesso_     </div>                   | <br>  </div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/white.png" style="height: 30px;"><br>Solido <br> </div> | <br><div style="text-align: center;"><img src="../img/reach/led-status/green.png" style="height: 30px;"><br>Pisca rápido </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/point-collection.gif" style="width: 150px;"></div>   |
|<br> <div style="text-align: center;">    Erro interno, <br>_assumindo que o Reach está_ <br> _no modo ponto de acesso_   </div>                   | <br>  </div>    |  <br> <div style="text-align: center;"><img src="../img/reach/led-status/white.png" style="height: 30px;"><br>Solido <br> </div> | <br><div style="text-align: center;"><img src="../img/reach/led-status/red.png" style="height: 30px;"><br>Solido </div>|<br>  <div style="text-align: center;"><img src="../img/reach/led-status/error.gif" style="width: 150px;"></div>   |
