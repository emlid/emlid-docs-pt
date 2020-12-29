Como o ReachView versão **0.3.0** Reach oferece suporte à saída de coordenadas aprimoradas por RTK para os pilotos automáticos Navio e Pixhawk. Para tornar isso possível, implementamos um protocolo personalizado que chamamos de **ERB** (Emlid Reach Binary protocol).

Aqui está um vídeo de demonstração com nossos resultados:
<div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/oq9H19ikAdM" frameborder="0" allowfullscreen></iframe></div>

## Especificação do protocolo ERB

A descrição do protocolo está disponível [here](https://files.emlid.com/ERB.pdf).

## Requisitos

O suporte do ERB está incluído no ArduPilot, começando com as seguintes versões:

* ArduCopter 3.4
* ArduPlane  3.5.0
* APMrover   3.1

## Configuração recomendada

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/reachm-ardupilot-scheme.png" style="width: 800px;"></div>

A configuração que recomendamos é a seguinte:

*	Navio ou Pixhawk com o firmware do ArduPilot (não menos que a versão 3.4.0 para ArduCopter, 3.6.0 para ArduPlane e 3.0.1 para ArduRover). É preferível usar a última versão estável
*	Estações base é uma unidade Reach RS/RS+ no modo Wi-Fi AP, configurada como um servidor TCP
*	O GCS é um laptop com o Mission Planner (versão 1.3.35 e superior), conectado à rede Wi-Fi do Reach.
*	Conexão de telemetria através de um rádio serial
*	A unidade Rover Reach M + é montada em um drone e conectada ao Navio ou ao Pixhawk através do fio 6P-to-6P. Esse tipo de conexão resolverá três problemas de uma vez: power Reach, permite que a placa ArduPilot passe por correções de base e permita que Reach passe a solução RTK de volta.


O guia a seguir mostrará como configurar o Navio ou o Pixhawk e o Reach para funcionar nessa configuração. Se você deseja alterar este fluxo de trabalho, deve ser bastante fácil fazê-lo, já que todas as partes do sistema são independentes das outras.




## Conectando Reach M+ a Pixhawk

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/pixhawk-reachm-radio.png" style="width: 500px;"></div>

Para fornecer a solução RTK para a Pixhawk, o Reach precisa estar conectado por meio de uma porta serial. Você pode fazer isso conectando o cabo serial na porta JST-GH do Reach e no conector **"Serial 4/5"** da Pixhawk.

!!! nota ""
	É recomendado fornecer o Reach M + a partir de uma fonte de energia externa. A Pixhawk pode não fornecer energia suficiente para o Reach em alguns casos.

## Conectando o Reach M+ ao Navio sobre o UART

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/navio2-reachm.png" style="width: 500px;"></div>

Conecte a porta JST-GH do Reach com a porta **UART** do Navio.

## Conectando o Reach M+ ao Navio via USB

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/navio2-reachm-usb.jpg" style="width: 500px;"></div>

Conecte a porta Micro-USB do Reach com a porta **USB** do RPi.

## Conectando o Reach M+ ao Edge

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/edge-reachm.png" style="width: 500px"></div>

Conecte a porta JST-GH do Reach com a porta SER1-I2C do Edge. O guia de integração Edge and Reach M+ pode ser encontrado em Documentação do Edge: [Integração do Reach](https://docs.emlid.com/edge/tutorials/reach-integration/).

## Configurando o Reach para trabalhar com o ArduPilot

### Configuração do rover

!!! nota
    A conexão serial é usada para aceitar correções de base e enviar a solução ao mesmo tempo.

Comece com a entrada de correção da base de configuração:

* Selecione a aba de **Correction input**
* Selecione  **Serial**
* Escolha **UART** ou **USB-to-PC** como o dispositivo
* Escolha a taxa de transmissão desejada (38400 por padrão)
* Escolha **RTCM3** como formato de correções base
* Clique no botão **Apply** para salvar as configurações

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/reach-base-correction-input.png" style="width: 100%;"></div>

Agora configure a saída de posição (Position output):

* Selecione a aba **Position output**
* Selecione **Serial**
* Escolha **UART** ou **USB-to-PC** como o dispositivo
* Escolha a taxa de transmissão desejada (38400 por padrão)
* Escolha **NMEA** como formato de saída de posição
* Clique no botão **Apply** para salvar as configurações

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/reach-position-output.png" style="width: 100%;"></div>

!!! nota
	**ERB** é um protocolo personalizado, usado para enviar dados de localização para o piloto automático.


### Configurando um link de correção

O Reach suporta várias maneiras de aceitar [correções da base](common/reachview/correction-input/#base-correction), incluindo os rádios seriais populares da área UAV. No entanto, ter um link de rádio separado para correções básicas é altamente ineficaz.

Para resolver isso, você pode usar o rádio de telemetria como uma portadora para correções RTK. O GCS pode passar essas correções para o piloto automático com um recurso chamado **GPS inject**. Essa funcionalidade está disponível somente no **Mission planner** .

### Configurando o rádio para incorporar correções na telemetria

Com as configurações padrão, a telemetria de rádio não é otimizada para o envio de correções RTK. Isso pode causar atrasos de entrega de dados de correção e até mesmo perda. Esses atrasos irão atrapalhar a qualidade da solução RTK, por isso precisamos minimizá-los.

!!! nota
    A configuração de rádio é feita com a telemetria desconectada.

Para alterar as configurações de rádio, verifique se a **Mavlink connection is disabled**. Em seguida, vá para o menu **Initial setup** e selecione **Sik Radio** no menu lateral. Clique em **Load settings** e aguarde os parâmetros dos dois rádios serem carregados.

Você precisa limpar o campo **ECC** e selecionar **Raw Data** no campo de seleção Mavlink.

Depois disso, clique em **Save settings**. Se o firmware do seu rádio estiver desatualizado, atualize com **Update Firmware(Local)**.


<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-radio-setup.png" style="width: 800px;"></div>

### Configurando o ArduPilot para aceitar a solução Reach

!!! Atenção
    Recomenda-se usar o Reach como uma segunda unidade GPS apenas.

Para iniciar o ArduPilot no Navio, adicione ao seu comando de partida um dos seguintes argumentos:

* Para conexão UART
```bash
-E /dev/ttyAMA0
```

* Para conexão USB
```bash
-E /dev/ttyACM0
```
Isso permitirá usar o Reach como GPS externo.

A configuração do ArduPilot exigirá a configuração de alguns parâmetros usando o Mission Planner. Após a conexão, vá para o menu **CONFIG/TUNING** e clique em **Full parameters list** à esquerda. Para encontrar o parâmetro desejado mais rapidamente, use uma caixa de pesquisa à direita (destacada em vermelho).

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-full-parameter-list.png" style="width: 800px;"></div>

StartComece com as configurações do parâmetro **GPS_TYPE2** para **"5"** - NMEA. Isso permitirá a segunda entrada do GPS

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-type2-parameter.png" style="width: 800px;"></div>

Em seguida, defina o parâmetro **SERIAL4_BAUD** para a mesma taxa de transmissão, conforme escolhido na saída da solução ReachView. Observe as opções correspondentes às diferentes taxas de transmissão.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-serial4-baud-parameter.png" style="width: 800px;"></div>

Defina **GPS_AUTO_SWITCH** para **"1"** - ativado. O piloto automático irá alternar automaticamente entre os dois receptores GPS, escolhendo aquele com melhor solução.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-auto-switch-parameter.png" style="width: 800px;"></div>

Finalmente, defina o parâmetro **GPS_INJECT_TO** para **"1"**. **"1"** aqui representa a segunda entrada do GPS. Se você configurou o Reach como a primeira entrada, defina este parâmetro como **"0"**.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-inject-to-parameter.png" style="width: 800px;"></div>

### Configurando Mission Planner para mostrar correções RTK em telemetria

Para habilitar e configurar as opções de “GPS Inject” no Mission Planner, pressione a combinação de botões **"ctrl+F"** Isso abrirá uma janela com configurações avançadas do GCS. Clique no botão **Inject GPS** direita.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-inject-settings.png" style="width: 70%;"></div>

Na nova janela, escolha os parâmetros para a conexão básica. O Reach no modo base suporta os modos TCP e serial. Para o propósito deste exemplo, **suponhamos que as correções básicas sejam provenientes de outro Reach configurado para envio de correção da base via TCP**. Esta é uma configuração que normalmente usamos em nossos voos de teste.

### Configuração de base

Vamos configurar nosso Reach:

* Abra a guia **Base mode** tabno Reach
* Escolha TCP nas opções “correction output”
* Definir **Server** no campo de função
* Definir 9000 como porta
* Clique no botão **Apply** para salvar as configurações

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/reach-base-mode.png" style="width: 100%;"></div>

Para conectar-se, escolha o modo “TCP Client” no Mission Planner.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-inject-connection-type-new.png" style="width: 80%;"></div>

Digite o endereço IP do Reach.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-inject-ip-new.png" style="width: 60%;"></div>

E o número da porta do servidor.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-inject-port-new.png" style="width: 60%;"></div>

Finalmente, verifique se as correções estão chegando.

<div style="text-align: center;"><img src="../img/reachm-plus/ardupilot-integration/mp-gps-inject-connected-new.png" style="width: 70%;"></div>
