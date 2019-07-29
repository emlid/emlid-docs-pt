## Onde obter o código

O Navio2 é suportado no upstream [Repositório ArduPilot](https://github.com/ArduPilot/ardupilot).

## Como construir

O binário do ArduPilot pode ser construído de deuas maneiras:

1) Diretamente no seu Raspberry Pi. Mais simples, mas mais lento. A compilação leva aproximadamente 15 minutos.

2) Usando um compilador cruzado (PC com Linux ou na máquina virtual). Isso é muito mais rápido, mas requer uma configuração única.

Se você gostaria de construir no Raspberry Pi pule o próximo passo.

## Configuração de compilador cruzado no Linux (opcional)

Compilador recomendado é aquele que é fornecido pela Fundação Raspberry Pi.Faça o download e extraia-o em algum diretório, por exemplo, em /opt/:

```bash
sudo git clone --depth 1 https://github.com/raspberrypi/tools.git /opt/tools
```

Se você estiver usando a distro de 32-bit, adicione o seguinte ao seu PATH:

```bash
export PATH=/opt/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian/bin:$PATH
```

Para distro de 64-bit, adicione isto ao seu PATH

```bash
export PATH=/opt/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian-x64/bin:$PATH
```

Se você gostaria de adicionar o compilador ao ambiente PATH, edite permanentemente o /etc/.

## Construindo o ArduPilot usando o sistema de compilação Waf

Estas etapas são as mesmas tanto para compilar o ArduPilot diretamente no Raspberry Pi quanto para compilação cruzada.

Faça o download do código do ArduPilot e atualize os submódulos:

```bash
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot
git submodule update --init --recursive
```  

Checkout to a specific tag in order not to fly off master.
<sub> `git tag` to get a list of tags </sub>

Por exemplo, para construir um binário de um arducopter:
```bash
git checkout ArduCopter-stable
or
git checkout ArduCopter-beta
```

Note que o Waf deve sempre ser chamado a partir do diretório raiz do ardupilot.

Para manter o acesso ao Waf conveniente, use o seguinte caminho do diretório raiz do ardupilot:  
```bash
alias waf="$PWD/modules/waf/waf-light"
```  
Diferentemente da construção baseada automação, com o Waf há uma etapa da configuração para escolher a placa a ser usada:
```bash
waf configure --board=navio2
```

Se o ```future``` não estiver instalado, você deverá instalá-lo:
```bash
pip install future
```

Agora você pode construiu o arducopter. Para um arducopter, use o seguinte comando:
```bash
waf copter
```  
No final da compilação, binários com o nome ```arducopter-quad``` seráo colocados no diretório ```ardupilot/build/navio2/bin/```.

!!! tip ""
    Sugerimos verifciar os documentos da ArduPilot para mais detalhes [aqui](https://github.com/ArduPilot/ardupilot/blob/master/BUILD.md). Está é a referência mais utilizada.

Se você estiver usando o compilador cruzado, transfira o binário para o seu Raspberry Pi:

```bash
rsync -avz ardupilot/build/navio2/bin/arducopter-quad pi@192.168.1.3:/home/pi/
```

Onde 192.168.1.3 é um endereço IP do seu Raspberry Pi com um Navio.


Instruções sobre como executar o ArduPilot no Raspberry Pi e conectar o GCS a ele estão disponíveis em [Seção de instalação e execução](installation-and-running.md).
