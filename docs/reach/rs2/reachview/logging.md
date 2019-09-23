#Gravação e download de logs

Este tutorial mostra como gravar logs para análise de dados e pós-processamento cinemático (PPK) e como fazer o donwload do Reach para o seu computador.

!!! tip ""
	Para saber mais sobre o PPK, leia [nossa introdução sobre o pós-processamento cinemático](../../tutorials/ppk-introduction).

##Período de divisão do log

Antes de iniciar a gravação do log, você pode especificar o período de divisão do log no ReachView [settings](settings.md). Por exemplo, se definirmos salvar o log a acada 4 horas, o novo arquivo de log será criado a cada 4 horas, preservando também o log anterior. Essa configuração permite controlar o tamanho dos arquivos com os quais você trabalha.

##Logging

Para ativar a gravação de logs, vá para a guia "Logging" no ReachView. Aqui você pode ver várias opções de log. O Reach pode registrar raw data (dados brutos),position log (log de posição)e base corrections (correções da base).

<p style="text-align:center" ><img src="../img/reachview/logging/enable-logging.png" style="width: 800px;" /></p>

<p style="text-align:center" ><img src="../img/reachview/logging/enable-logging.gif" style="width: 800px;" /></p>

###Raw data (Dados brutos)

Um log raw data contém observações GNSS do receptor sem cálculo de coordenadas precisas. Pode ser gravado em UBX ou diretamente no formato RINEX padrão da indústria. O UBX pode ser convertido em RINEX com o RTKCONV após o donwload para o seu PC. Se você não souber qual deles precisa, recomendamos o uso do RINEX 3.03.

As time marks para o mapeamento UAV também são armazenados nesse arquivo.

!!! note ""
    Durante a gravação no formato RINEX, o arquivo UBX é registrado como backup.

###Position (Posição)

Um log Position pode ser registrado em diferentes formatos. Abra a lista suspensa para escolher o formato para as coordenadas de posição.

!!! note ""
	Aqui está uma breve visão geral dos formatos. Descrições mais detalhadas dos formatos podem ser encontradas na seção Position output (Sáida de posição) [docs](../../reachview/position-output/#formats).

* **LLH**

LLH é um simples protocolo de texto que contém longitude, latitude e altura em WGS84. Ele também contém informações sobre o status da solução RTK.

* **XYZ**

XYZ é um simples protocolo de texto para a coordenadas X, Y, Z ECEF, bem como o status da solução. 

* **ENU**

ENU  também é um simples protocolo de texto para os componentes leste, norte e UP da linha de base, bem como o status da solução.

* **NMEA**

NMEA 0183 é o padrão mais popular do setor. Geralmente é suportado pela maioria dos softwares e hardwares. Mensagens NMEA suportadas: GPRMC, GPGGA, GPGSA, GLGSA, GAGSA, GPGSV, GLGSV, GAGSV. 

* **ERB**

O formato ERB é usado para comunicação com o Ardupilot.

###Base corrections (Correções de base)

A última opção de log é a base corrections. Esse formato de log é definido pelas correções que o Reach aceita da base. Se você usar a base Reach, o log será gravado em RTCM3.

##Baixando

Após concluir os registros em campo, você pode salvar os logs no seu Mac, Windows, Linux ou dispositivo móvel. Você pode fazer isso na mes aguia "Logging" no ReachView.

Desative as alternância <img src="../img/reachview/logging/toggle.svg" align="middle" /> para interromper o registro dos logs. Econtre os seus registros abaixo na guia  "Logging" no ReachView.

<p style="text-align:center" ><img src="../img/reachview/logging/download-logs.gif" style="width: 800px;" /></p>

Você pode ver a data e hora da gravação. 

Existem dois botões no lado direito de cada log: <img src="../img/reachview/logging/blue-arrow.svg" align="middle" alt="blue arrow" />  o botão permite salvá-lo, e o botão <img src="../img/reachview/logging/garbage-can.svg" align="middle" alt="red garbage can" /> deletar.

Agora, quando os logs são baixados, você pode usar o [software RTKLIB](../../tutorials/gps-post-processing) nos documentos da Emlid para começar a trabalhar com seus dados.

Verifique o [guia PPK](../../tutorials/gps-post-processing) nos documentos da Emlid para saber mais sobre o PPK.

