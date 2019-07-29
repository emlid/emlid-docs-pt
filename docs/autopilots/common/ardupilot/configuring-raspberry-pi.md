## Download da imagem Raspbian configurada

O Navio requer um Raspbian pré-configurado para ser executado. Nós fornecemos uma imagem de cartão SD unificada para Raspberry Pi 2 e 3. O sistema operacional é sem cabeça, ou seja, ele vem sem GUI, pois não é necessário para aplicações de drone.

[Baixe a imagem do cartão SD com a versão mais recente do Raspbian (Stretch)](http://files.emlid.com/images/emlid-raspbian-20190227.img.xz), [(md5)](https://files.emlid.com/images/MD5SUMS)

## Escrever imagem no cartão SD

* Obtenha a última imagem do Emlid Raspbian.
* Baixe, extraia e execute no [Etcher](https://etcher.io/) como administrador.
* Selecione o arquivo com a imagem e a letra da unidade do cartão SD.
* Clique em “Flash!”. O processo pode demorar alguns minutos.

<iframe  title="Emlid manuals" width="680" height="380" src="https://www.youtube.com/embed/i8_TFYWYt_M" allowfullscreen></iframe>

Instruções mais detalhadas estão disponíveis [aqui](http://www.raspberrypi.org/documentation/installation/installing-images/).

## Configurando o acesso ao Wi-Fi

O Raspberry Pi3 possui um módulo Wi-Fi interno, enquanto o Raspberry Pi 2 requer um adaptador de USB Wi-Fi externo. Uma extensa lista de adaptadores suportados está disponível [aqui](http://elinux.org/RPi_USB_Wi-Fi_Adapters).

As redes Wi-Fi podem ser configuradas editando o arquivo wpa_supplicant.conf localizado no cartão SD (partição /boot). Para adicionar sua rede, basta adicionar as seguintes linhas a ele:

```bash
network={
  ssid="yourssid"
  psk="yourpasskey"
  key_mgmt=WPA-PSK
}
```

Para obter acesso a esta arquivo, use um dos seguintes métodos:

### Editar configurações no cartão SD

Basta conectar um cartão SD no seu computador. Depois de obter acesso ao conteúdo do cartão SD, abra o wpa_supplicant.conf localizado na partição /boot (com privilégios da raiz no Linux) e edite o arquivo conforme descrito acima.

### Use monitor e teclado

Conecte o monitor HDMI e o teclado USB ao seu Raspberry, ligue-o e você terá acesso ao console, onde você pode usar o editor de texto para modificar o wpa_supplicant.

!!! note ""
	Use o nome de usuário padrão `pi` e a senha padrão `raspberry` para obter acesso ao seu RPi.

Depois de entrar no sistema, digite:

```bash
sudo nano /boot/wpa_supplicant.conf
```

Modifique o arquivo como descrito acima, salve e reinicie.
Este método pode ser problemático porque alguns teclados não são compatíveis com este Kernel. Se o seu teclado não funcionar, tente outro ou use outro método.

### Use Ethernet

Você pode se conectar ao Raspberry Pi pela Ethernet conectando-o usando um cabo Ethernet a um switch, roteador ou diretamente ao seu computador.

### Tentando se conectar usando o Zeroconf

Há uma boa chance de você poder usar o seu Raspberry Pi usando o Zeroconf.

Você pode tentar ```ssh pi@navio.local``` no Mac ou Linux ou digitar navio.local no Putty no Windows.

Se isso não funcionar para você, leia uma seção abaixo.

### Encontrando um endereço IP

Para encontrar um endereço IP do seu Raspberry Pi, use o utilitário nmap.

Pode ser executado a partir do console na sua área de trabalho:
nmap -sn 192.168.1.*

Você pode usá-lo com uma GUI, como Zenmap ou aplicativo Fing no seu telefone.

Procure o hostname ”navio”.

### wpa_passphrase no Linux

Se você editar o arquivo em um Raspberry ou em um computador Linux, você pode preencher o **wpa_supplicant.conf** com um utilitário chamado **wpa_passphrase** desta forma:

```sudo bash -c "wpa_passphrase SSID password" >> /boot/wpa_supplicant.conf```

## Atualizando

Se necessário, você pode atualizar seu sistema executando:

```sudo apt-get update && sudo apt-get dist-upgrade```

## Expansão de rootfs

Por padrão, quando o Emlid Raspbian para o Raspberry Pi é instalado no sistema de arquivos expandirá apenas para ocupar o 3GB de armazenamento. Se você não tem espaço no seu dispositivo, você deve expandir seu sistema de arquivos. Para fazer isso, basta digitar

```sudo raspi-config --expand-rootfs```

e reinicie.
