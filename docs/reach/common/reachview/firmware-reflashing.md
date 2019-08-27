Nestsa página, você encontrará as informações sobre como realizar o reflash de firmware do Reach.

Observe que você **não** precisa fazer isso, a menos que queira levar o Reach ao estado inicial.

!!! tip ""
	A maiora dos novos recursos são lançados por meio do aplicativo ReachView e pode ser atualizado simplesmente por meio de sua interface. Mais informações sobre como atualizar o aplicativo ReachView estão disponíveis na [seção de introdução](../../reachview/#updating).

??? note "Guia do flash de firmware para o Reach RS2 / RS+ / M+"

	### Download do firmware do Reach RS2 / RS+ / M+

	Obtenha a versão mais recente da imagem do ReachView e descompacte-a:

	<center>
	
	|Para o Reach RS2|Para o Reach RS+ / M+|
	|:-------------:|:-------------:|
	|[**Reach RS2 Image v2.20.7 [ZIP, 358.7 MB]**](http://files.emlid.com/images/reach-rs2-v2.20.7.zip), [(md5)](http://files.emlid.com/images/reach-rs2-MD5SUMS)|[**Reach RS+/M+ Image v2.18 [ZIP, 347 MB]**](http://files.emlid.com/images/reach-plus-v2.18.1.zip), [(md5)](http://files.emlid.com/images/reach-plus-MD5SUMS)|

	</center>
	

	### Download do Reach Firmware Flash Tool

	!!! note "" 
		Enquanto isso, use os sistemas operacionais **Windows** ou **Linux** para exibir seus dispositivos Reach RS2 / RS+ / M+. O Reach Firmware Flash Tool para o **Mac OS X** estará disponível em breve.
	
	* Obtenha o Reach Firmware Flash Tool:

	<center>
	
	|Windows|Linux|
	|:-------------:|:----------:|
	|[Download [EXE, 78.3 MB]](http://files.emlid.com/flash-tools/win/reach-firmware-flash-tool_1.0.2_setup.exe)|[Download [DEB, 51.9 MB]](http://files.emlid.com/flash-tools/linux/reach-firmware-flash-tool_1.0.0_amd64.deb)|

	</center>

	* Clique duas vezes no arquivo baixado
	
	* Siga as instruções para instalar o Reach Firmware Flash Tool no seu PC

	### Processo de flashing

	* Abra o Reach Firmware Flash Tool e escolha o modelo de Reach

	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step1-device-select.png" style="width: 300px;" /></p>

	<!-- delete part with RS -->

	* Selecione o arquivo .img do firmware do ReachView

	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step2-image-select.png" style="width: 300px;" /></p>

	* Desconecte todas as unidades do Reach. Se não houver nenhuma, o Flash Tool pulará automaticamente esta etapa
	
	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step3-disconnect-devices.png" style="width: 300px;" /></p>

	* Conecte o dispositivo Reach e ligue-o. A mensagem "Reach conectado" será exibida

	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step4-connected-reach.png" style="width: 300px;" /></p>

	* Espere até o final do processo de flash

	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step5-flashing.png" style="width: 300px;" /></p>

	* Após o reflashing, o Reach será reinicializado

	!!! danger ""
		Não desconecte o Reach nesta etapa.

	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step5-rebooting.png" style="width: 300px;" /></p>

	* Quando o Reach for reinicializado com sucesso, você verá a mensagem "Reach is flashed and ready to use" e estará pronto para o uso.

	<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-step5-flashed-reach.png" style="width: 300px;" /></p>

	??? danger ""Flashing failed" erro no flash"

		Se aparecer o erro "Flashing failed", recomendamos que siga as próximas etapas:

		<p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/app-flashing-failed.png" style="width: 300px;" /></p>

		??? note "Etapa para o Reach RS2"
			
			* Desconecte o dispositivo **Reach RS2** do PC
			
			* Segure o botão liga/desliga por 10 segundos até que o Reach desligue

			* Pressione o botão *Try again* no Reach Firmware Flash Tool no PC

			* Agora você precisa entrar no no modo Firmware Update. Para ativá-lo no Reach RS2, pressione e segure o botão liga/desliga e, em seguida, conecte o USB ao PC. Todos os LEDs devem piscar várias vezes simultaneamente e começar a piscar um após o outro.
			<br> <p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/failed-rs2.gif" style="width: 400px;" /></p>


		??? note "Etapa para o Reach RS+"
			
			* Desconecte o dispositivo **Reach RS+** do PC
			
			* Segure o botão liga/desliga por 10 segundos até que o Reach desligue

			* Pressione o botão *Try again* no Reach Firmware Flash Tool no PC

			* Agora você precisa entrar no no modo Firmware Update. Para ativá-lo no Reach RS+, pressione e segure o botão liga/desliga e, em seguida, conecte o USB ao PC. Todos os LEDs devem piscar várias vezes simultaneamente e começar a piscar um após o outro. 
			<br> <p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/failed-rs-plus.gif" style="width: 400px;" /></p>
		
		
		??? note "Etapa para o Reach M+"
			
			* Desconecte o dispositivo **Reach M+**do PC

			* Pressione o botão *Try again* no Reach Firmware Flash Tool no PC

			* Agora você precisa entrar no modo Firmware Update. Para ativá-lo no Reach M+, use o pino para pressionar e manter pressionado o botão localizado próximo ao LED de energia e , em seguida, conecte o USB ao PC. Nenhum LED deve piscar.
			<br> <p style="text-align:center" ><img src="../img/reachview/firmware-reflashing/failed-m-plus.gif" style="width: 400px;" /></p>

	### Depois do flashing

	Se o flash tiver sido completado com sucesso, você verá a mensagem "Reach is flashed and ready to use" e o dispositivo estará pronto para o uso. Você pode desconectar seu Reach neste momento.

	Prossiga para seção guia rápido para configurar o seu Reach RS2, RS+ ou Reach M+:

	* [Guia rápido para Reach RS2](https://docs.emlid.com/reachrs2/quickstart/)
	* [Guia rápido para Reach RS+](https://docs.emlid.com/reachrs/quickstart/first-setup)
	* [Guia rápido para Reach M+](https://docs.emlid.com/reachm-plus/quickstart/)

??? note " Guia para o flash de firmware do Reach RS / RTK"

	### Download do firmware do Reach RS / RTK

	Obtenha a versão mais recente da imagem ReachView:

	<center>
	
	|Download link|
	|:-------------:|
	|[**Reach Image v2.18 [ZIP, 234 MB]**](https://files.emlid.com/images/ReachImage_v2.18.1.zip), [(md5)](https://files.emlid.com/images/reachview-MD5SUMS)|

	</center>

	### Processo de flashing

	??? note "Etapa para o Windows"

		#### Windows

		Antes do flashing:

		* Instale o [Intel Edison driver](http://files.emlid.com/firmware-reflashing-tool/IntelEdisonDriverSetup1.2.1.exe)
		* Descompacte a imagem baixada
		* Download da cópia do [dfu-util.exe](https://files.emlid.com/images/dfu-util/dfu-util.exe) e [libusb-1.0.dll](https://files.emlid.com/images/dfu-util/libusb-1.0.dll)
		* Coloque esses arquivos na mesma pasta que os arquivos da imagem
		* Desconecte o Reach se ele estiver conectado

		Flash:

		1. Navigue até o diretório de imagens
		2. Execute `flashall.bat`
		3. Plug o Reach
		4. Monitore o progresso na janela do terminal
		5. Prossega para seção "Depois do flashing" abaixo


	??? note "Etapa para o Mac OS X"
		
		#### Mac OS X

		Antes do flashing:

		* Descompacte a imagem baixada
		* Instale o **[homebrew](http://brew.sh)**
		* Instale o anexo com `brew install dfu-util coreutils gnu-getopt lsusb`
		* Desconecte o Reach se ele estiver conectado

		Flash:

		1. `cd` no diretório de imagens
		2. Execute `./flashall.sh`
		3. Plug o Reach
		4. Monitore o progresso na janela do terminal
		5. Prossega para seção "Depois do flashing" abaixo


	??? note "Etapa para o Linux"

		#### Linux

		Antes do flashing:

		* Descompacte a imagem baixada
		* Instale o dfu-util com o comando `sudo apt-get install dfu-util`
		* Desconecte o Reach se ele estiver conectado

		Flash:

		1. `cd` no diretório de imagens
		2. Execute `sudo ./flashall.sh`
		3. Plug o Reach
		4. Monitore o progresso na janela do terminal
		5. Prossega para seção "Depois do flashing" abaixo

	## Depois flashing

	Depois que o processo inicial for concluído, o Reach será reinicializado. 
	
	!!! danger ""
		Não desconecte-o até que ele seja reinicializado e passe completamente pelo processo de configuração inicial.


	Continue na seção guia rápido para configurar o seu Reach RS / RTK:

	* [Guia rápido para Reach RS](https://docs.emlid.com/reachrs/quickstart/first-setup)
	* [Guia rápido para Reach RTK](https://docs.emlid.com/reach/quickstart/)
