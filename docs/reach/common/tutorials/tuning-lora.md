#Configurando LoRa para coleta de dados RTK

##Visão geral

Este guia explica como configurar rádios LoRa na base e rover Reach para RTK.

!!! tip ""
	Nos guias de vídeo de configuração Base e Rover, mostramos as configurações recomendadas para LoRa. Essas configurações devem funcionar bem na maioria dos casos, portanto, verifique primeiro o vídeo:

    ??? note "Configurando RTK no Reach RS2 base e rover através do rádio LoRa"
        
        <center>

	    <div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/-K32ayVmH6U" allowfullscreen></iframe></div>

	    </center>

    ??? note "Configurando RTK no Reach RS/RS+ base e rover através do rádio LoRa"
        
        <center>

	    <div style="text-align: center;"><iframe width="560" height="315" src="https://www.youtube.com/embed/4GfUDoDwEAE" allowfullscreen></iframe></div>

	    </center>

## Configuração LoRa

Existem vários fatores que podem afetar o alcance dos rádios LoRa do Reach RS/RS+ e Reach RS2:

* Condições do ambiente
* Configuração no aplicativo ReachView
* Configuração de hardware no campo

Siga este simples checklist para garantir que sua configuração seja ideal:

* Verifique se as antenas LoRa estão firmemente conectadas

* Use as mesmas configurações de LoRa na guia **"Base mode"** (Modo base) na base e em **"Correction input"** (Entrada de correção) no rover. Aqui estão as configurações recomendadas:
    - "Frequency" padrão definida pelo aplicativo
    - 20 dBm "output power"
    - 9.11 kb/s "air data rate"

??? "Configuração da base"
    <div style="text-align: center;"><img src="../img/reach/tuning-lora/base-mode.png" style="width: 800px;"></div>

??? "Configuração do rover"
    <div style="text-align: center;"><img src="../img/reach/tuning-lora/correction-input.png" style="width: 800px;"></div>

* Verifique os arredores. Na linha de visão, a linha de base pode atingir até 8 quilômetros ([ou algumas vezes até 19km](https://emlid.com/reach-rs-integrated-radio-hits-19-2-km-baseline/)) enquanto em uma área de vegetação densa, o alcance pode ser reduzido para centenas de metros. Verifique se não há obstáculos que possam reduzir o alcance

## Configurações avançadas

Para melhorar ainda mais o alcance LoRa, use as sugestões abaixo.

### Air data rate

A alta taxa de dados fornece um fluxo de correção mais estável que permite transmitir um número maior de mensagens RTCM3. A escolha de valores mais baixos da taxa de dados, pelo contrário, limita o número de mensagens do RTCM3, mas pode aumentar significativamente a linha de base.

!!! tip ""
    Quanto menor o "air data rate", maior será a distância de trabalho.

* Verifique sua seleção de mensagens RTCM3 na guia **"Base mode"** (Modo base) na unidade base. Caso você use GPS e GLONASS nas configurações RTK, as seguintes mensagens deverão ser ativadas:

??? "Reach RS+ base"
    * 1002 (GPS L1 Observations), 1 Hz
    * 1006 (ARP station coordinate), 0.1Hz
    * 1010 (GLONASS L1 observation), 1 Hz
    
    <div style="text-align: center;"><img src="../img/reach/tuning-lora/rtcm-selection.png" style="width: 800px;"></div>

??? "Reach RS2 base"
    * 1006 (ARP station coordinate), 0.1 Hz
    * 1074 (GPS MSM4), 1 Hz
    * 1084 (GLONASS MSM4), 1 Hz

* Teste a configuração com valores mais baixos de taxa de dados: 4,56 kb/s e, em seguida, 2,6 kb/s

!!! note ""
    Certifique-se de alterar a "air data rate" nos receptores base e rover:

    * Aba **Base mode** (Modo base) da base
    * Aba **Correction input** (Entrada de correções) do rover

### Frequency

Às vezes, a faixa de frequência permitida na sua área de trabalho pode ser afetada por alguns fatores locais. É por isso que é importante encontrar uma frequência que funcione de forma eficiente para suas condições ambientais.

* Verifique que você utilizou [configuraçoes padrões para o LoRa mencionadas acima](#configuracao-lora)

* Verifique novamente quais faixas de frequência que podem ser usadas na sua área

!!! danger ""
	Algumas bandas de frequência podem não ser permitidas na sua região. Atualmente, essas limitações são aplicadas automaticamente no ReachView em alguns países.

* Configure a frequência no valor mais alto permitido

!!! note ""
	Certifique-se de configurar a mesma frequência nos dispositivos base e rover:
    
    * Aba **Base mode** (Modo base) da base
    * Aba **Correction input** (Entrada de correções) do rover

* Verifique a distância máxima utilizando LoRa que você pode obter com essa frequência. Se a faixa não for suficiente, desça na etapa de 1-2 MHz até encontrar a frequência que funciona melhor para sua área

<br>

Se você ainda tiver dificuldades em ajustar as configurações de LoRa, não hesite em nos contatar em support@emlid.com ou crie um tópico no [forum da comunidade Emlid](https://community.emlid.com/c/international-discussion/portuguese) com todas as suas dúvidas!
