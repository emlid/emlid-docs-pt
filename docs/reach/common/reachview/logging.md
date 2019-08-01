#Coletare e fazer o download dos logs

Este tutorial mostra como registrar os logs para análise de dados e pós-processamento cinemático (PPK) e como baixá-los do Reach para o seu computador.

!!! tip ""
	Para saber mais sobre o PPK leia [este artigo](../../tutorials/ppk-introduction).

##Período de devisão de log

Antes de iniciar a gravação do log, você pode especificar o período de registro no ReachView [configurações](settings.md). Por exemplo, se definirmos para salvar o log a cada 4 horas, o novo arquivo de log será criado a cada 4 horas, preservando também o log anterior. Essa configuração permite controlar o tamanho dos arquivos com os quais você trabalha.

##Logging

Para iniciar o registro dos logs, vá para a guia "Logging" no ReachView. Aqui você pode ver várias opções de log. O Reach pode registrar dados brutos (raw data), registro de posição (position) e correções de base (base correction).

<p style="text-align:center" ><img src="../img/reachview/logging/enable-logging.png" style="width: 800px;" /></p>

<p style="text-align:center" ><img src="../img/reachview/logging/enable-logging.gif" style="width: 800px;" /></p>

###Raw data

O log raw data contém as observações GNSS do receptor sem o cálculo de coordenadas precisas. Pode ser gravado em UBX ou diretamente no formato RINEX padrão da indústria. O UBX pode ser convertido em RINEX com o software RTKCONV após o download para o seu PC. Se você não sabe qual deles é necessário, recomendamos usar o RINEX 3.03.

Time marks para mapeamento UAV também são armazenadas nesse arquivo.

###Position

O log de posição pode ser registrado em diferentes formatos. Abra a lista para escolher o formato das coordenadas de posição.

!!! note ""
	Aqui está uma visão geral dos formatos. A descrição mais detalhada dos formatos podem ser encontradas na seção Position output[docs](../../reachview/position-output/#formats).

* **LLH**

O LLH é um simples protocolo de texto para Latitude, Longitude e Altura em WGS84. Ele também contém informações sobre o status da solução RTK.

* **XYZ**

O XYZ é um simples protocolo de texto para coordenadas ECEF X, Y, Z, bem como o status da solução. 

* **ENU**

O ENU tembém é um simples protocolo de texto para os componentes Leste, Norte e UP da linha de base, bem como o status da solução.

* **NMEA**

O NMEA 0183 é o padrão mais popular na indústria. Geralmente é suportado pela maioria dos softwares e hardwares. Mensagens NMEA suportadas: GPRMC, GPGGA, GPGSA, GLGSA, GAGSA, GPGSV, GLGSV, GAGSV. 

* **ERB**

O formato ERB é usado para comunicação com o Ardupilot.

###Base corrections

A última opção de log é a correção básica. Esse formato de log é definido pelas correções aceitas pelo Reach da base. Se você usar o Reach como base, esse log será registrado cem RTCM3.

##Baixando os logs

Depois de concluir a coleta, você pode salvar os logs em seu Mac, Windows, Linux ou dispositivo móvel. Você pode fazer isso na mesma guia "Logging" no ReachView.

Clique em <img src="../img/reachview/logging/toggle.png" align="middle" /> para interromper a coleta dos logs. Encontre os seus logs abaixo na guia "Logging" no  ReachView.

<p style="text-align:center" ><img src="../img/reachview/logging/download-logs.gif" style="width: 800px;" /></p>

Você pode ver a data e o horário da gravação. 

Existem dois botões no lado direito de cada log: <img src="../img/reachview/logging/blue-arrow.png" align="middle" alt="blue arrow" />  este botão permite baixar o log, and <img src="../img/reachview/logging/garbage-can.png" align="middle" alt="red garbage can" /> este botão exclui o log.

Agora, após baixar os logs, você pode usar o [software RTKLIB](../../tutorials/gps-post-processing) encontrado nos documentos da Emlid para começar a trabalhar com seus dados.

Verifique o [guia PPK](../../tutorials/gps-post-processing) encontrado nos documentos da Emlid para saber mais sobre o PPK.
