
### SoftOSD
-------

**Aviso legal**

O SoftOSD é um projeto pessoal do membro da comunidade da Emlid, George Andrikopoulos.

Para qualquer suporte, por favor, refira-se a ele no For any support please refer to him in the [Tópico do projeto](http://community.emlid.com/t/raspberry-pi-osd-using-navio/725/58).

Todo o texto a seguir foi fornecido pelo autor do projeto.

**Fim do aviso**

Está é a página DOC do software SoftOSD, que é uma versão "clássica" do hardware OSD (OnScreen Display).

O SoftOSD é o resultado da existência do NAVIO+, que é rico em grandes possibilidades e oportunidades de desenvolvimento.

Este software é um software fechado, o que significa que o código-fonte não está disponível para o público. Todas as características do software são fornecidas a partir da plataforma Raspberry Pi 2 da estrutura NAVIO+ com grande capacidade de desenvolvimento.

O software é escrito em Qt Language com algumas adições declarativas no QML. É muito leve em termos de tamanho (~80kb) e usa técnicas avançadas de software em sua implementação e função.
Utiliza 4 tarefas principais que se comunicam com o NAVIO+:

a. Tarefa de 1s
  Este segmento é usado para as comunicações de média prioridade, como nível de bateria e consumo em mAh.
b. Tarefa de 10s
  Este segmento é usado para a prioridade mais baixa, como os valores barométricos e de temperatura.
c. Tarefa de  40ms
  This thread is used for the highest priority sensors and feed like compass and Gyro Values.
d. Tarefa de 5s
  Este é um segmento de reposição para uso futuro, como o Audio Modem e outros sensores.
Não é garantido que as tarefas funcionem em seus eventos chamado Timed, mas os testes mostraram que deslocamentos menores de um dígito foram encontrados em casos de estresses. 

O SoftOSD foi totalemnte depurado e encontrado sem vazamentos de memória, nem mesmo em suas bibliotecas usadas. Isso torna seguro o uso de softwares no ambiente Raspberry Pi. O ArduPilot não foi testado com o SoftOSD na época, mas qualquer uso desses dois software é certo que funcionará.
Claro que, em qualquer caso, isso não significa que eu assumo qualquer responsabilidade por qualquer dano que possa ocorrer devido a falhas no ArduPilot. O SoftOSD não realiza nenhuma ações nos sensos do NAVIO+ nem altera sua natureza, o que significa ... ele apenas lê dados.

### Instalação
------------
Como afirmei acima, o SoftOSD é escrito em Qt e C++, o que o torna um comlexo "bit" para distribuir para outros, exceto aqueles que têm acesso ao ambiente de desenvolvimento. Para que todos (usuários e desenvolvedores) estejam na mesma página, eu distribuí a imagem de desenvolvimento do cartão SD do Raspberry Pi para a comunidade. O SoftOSD é desenvolvido diretamente no Pi (sem o uso de compiladores cruzados) e o ambiente é baseado na última imagem do NAVIO+ NATIVO PARA ORaspberry Pi 2.

### Requisitos
-------------
1. Cartão SD para NAVIO de 8GB.
2. Raspberry Pi 2 (1GB Ram)
3. NAVIO+ Autopilot
4. Raspberry Cabo para TV/Audio (https://www.raspberrypi.org/forums/viewtopic.php?f=91&t=83446)

O quarto requisito é muito importante, pois os cabos podem parecer iguais com os outros, mas o cabeamento interno é completamente diferente. Então, por favor, tenha muito cuidado ao comprar/construir o cabo. Se você construir o cabo, leve em considereação que os cabos de aúdio serão necessários no futuro e será bom que eles sejam construídos agora (Audio Modem etc).

### Instruções

1. Baixe a imagem pelo link abaixo
<    >

2. Salve a imagem no SD de sua escolha (8GB no mínimo)
3. Instale o SD no Raspberry com o NAVIO+ e carregue o sistema.
4. Efetue o login e execute os seguintes comandos no terminal (SSH Putty is fine)
  export QT_QPA_EGLFS_PHYSICAL_WIDTH=720
  export QT_QPA_EGLFS_PHYSICAL_HEIGHT=480
  Isso dirá ao Qt qual é o tamanho do buffer de quadros, já que nenhum dispositivo /dev/fb0 existe ou a consulta não responde.
5. Mover para a pasta cd /home/pi/SoftOSDv0.57/softOSD
6. Execute o sudo nano /boot/config.txt
   remover comentário de #sdtv_mode=2
   Isso permitirá o SDTV OUT (Composição do Raspberry Pi)
7. Remova qualquer cabo HDMI e reinicie (sudo reboot)
8. Mover para a pasta cd /home/pi/SoftOSDv0.57/softOSD
9. Execute --sdtvon "PAL 16:9"
    Isto irá ligar o composto TVOUT se você tiver o cabo HDMI conectado, o monitor ficará em branco.
---------------------------------------------------------------------------------------------------
Todas as etapas acima estão preparando o Raspberry Pi para uso pelo SoftOSD, ele não afetam o console.
Agora vamos usar um truque para que a câmera e o aplicativo sejam "sobrepostos".

10. Execute raspivid -t 0 -fps 25 -op 150 &
    Isto irá executar a pré-visualização de víddeo da Raspicam e exebi-lo na saída do Raspberry.
    Vamos verificar as opções do comando.

    -t 0 -> Informa ao programa para executar a pré-visualização da câmera indefinidamente (geralmente a visualização é executada por 5-8 segundos)

    -fps 25 -> Informa ao programa para obter 25 quadros por segundo a partir da exibição da câmera

    -op 150 -> Esse é o truque. Isso indica à câmera quase a metade da opacidade do buffer de quadros.
              Já que a visualização da câmera e todas as outras visualizações ao vivo do PiCamera sobrepõem qualquer coisa que seja executada atualmente (coloca tudo em segundo plano) eu uso o truque de opacidade para exibir o SoftOSD no plano de fundo.

    & -> Informe ao programa (raspivid) para executar como um serviço em segundo plano. Se você quiser parar o serviço, simplesmente execute sudo pkill raspivid.


11. Executar ./softOSD
    O programa será executado e o sistema obterá o Gyro Cablibrated e calculará as compensações.
    Você verá na tela o gimbals rolando e se estabilizando na posição atual do NAVIO+.
    Este é um efeito visto na vida real HUD na maioria dos aviões de combate ... não é meu ... é efeito sensor.    

### Comentários adicionais
    -------------------

A imagem é fornecida como está e pode ser usada para o desenvolvimento do Qt com suporte multimídia.
A estrutura foi construída nativamente (sem compilação cruzada) e todo o desenvolvimento é executado na plataforma.
Além disso, a imagem tem todos os aplicativos necessários para o ArduPilot e streaming de vídeo como gstreamer 1.0 etc.

### Dispositivos V4L2 (USB etc)
    ----------------------

A imagem é compatível com a estrutura V4L2. Isso significa que você pode substituir o comando raspivid com a alternativa v4l2-ctl com uma câmera de sua escolha. Como você já sabe, as câmeras USB não são rádpidas o suficiente para Pi (problemas de USB), mas a resolução é "baixa" (720 x480) e será mais próxima da realidade, já que os sensores serão muito mais rádpidos que o moviemnto. Questão menor como os dados do sensor/movimento e o vídeo são "sincronizados" no Pi e eles chegam à sua própria realidade no Trasmited Destination.

### GSTREAMER
    ---------

O gStreamer pode ser usado como foi usado antes os comandos que você usou para "raspivid -t 0 -h 720 -w 1080 -fps 25 -hf -b 2000000 -o - | gst-launch-1.0 -v fdsrc ! h264parse !  rtph264pay config-interval=1 pt=96 ! gdppay ! tcpserversink host=YOUR_RPI_IP_ADDRESS port=5000"
    Interromper entre o | e o comando raspivid o ./softOSD.

Isso irá transmitir todo o buffer de quadros, incluindo o SoftOSD, para o fluxo pipeline.
Eu ainda não testei, mas tenho certeza que vai funcionar. Se não houver uma solução, precisaremos de  tempo para encontrá-la.
Não esqueça de alterar a resolução do raspivid para -h 480 -w 720, senão o SoftOSD será uma bagunça. Não há uma escala adequada ... ainda.
