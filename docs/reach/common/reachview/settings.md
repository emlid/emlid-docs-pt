<p style="text-align:center" ><img src="../img/reachview/settings/settings.png" style="width: 800px;" /></p>

### Verifique a versão do aplicativo  
Toda vez que você liga o Reach em uma rede Wi-Fi, ele verifica se há uma nova atualização para ReachView e o notifica.

!!! Nota ""
    A verificação de atualização é feita apenas uma vez durante o processo de inicialização. Se você quiser forçar a nova versão, por favor, vá para o ReachView Updater. Está disponível na porta 5000, por exemplo http://reach.local:5000. Ele verificará automaticamente os servidores de atualização do Emlid quando você abri-lo. Saiba mais sobre o ReachView Updater [aqui](updater).

### Modo noturno
O modo noturno permite que você desligue os LEDs até a próxima reinicialização do dispositivo.

### Configurações do conector inferior
Ativa a inicialização automática usando o conector inferior no Reach RS +. Perfeito para integrar o receptor com carros ou tratores.

### Relatório do sistema
A ferramenta é usada para facilitar os relatórios de problemas. Existem dois tipos: um em texto simples e outro como um arquivo zip. O primeiro é para o fórum e facilita o compartilhamento de configurações, estado da rede e versão do aplicativo. O último é para casos mais difíceis e contém registros do sistema e detalhes técnicos do seu dispositivo.

!!! note "Gerando um relatório do sistema"
	<p style="text-align:center"><img src="../img/reachview/settings/system-report.gif" style="width: 800px;" /></p>

### Alterar nome do Reach  
O nome do Reach pode ser alterado para distinguir entre vários dispositivos. Um padrão muito comum é denominar dispositivos de acordo com sua função base ou rover. O nome do dispositivo é a base para o nome do ponto de acesso e o nome da rede local. O nome padrão é "reach", a alteração também afeta o nome local `http://reach.local` o nome do ponto de acesso `reach:xx:xx`.

### Redefinir as configurações para o padrão  
Clique no botão “Redefinir as configurações para o padrão” para retornar todas as configurações para a configuração de fábrica. Apenas registros e configurações sem fio são mantidos. Se você gostaria de realizar uma reinicialização de fábrica completa e limpar todos os seus dados, você pode usar o [reflash imagem do firmware](firmware-reflashing).

### Alterar a senha do ponto de acesso
A senha padrão do ponto de acesso é “emlidreach”, você pode alterá-la por motivos de segurança. Se você esquecer sua nova senha de ponto de acesso, ainda poderá acessar o Reach, levando-o a uma rede Wi-Fi conhecida. Se você perder o acesso ao Reach, poderá usar o [reflashreflash image firmware](firmware-reflashing) e configurá-lo novamente.

### Configurações de log
Especifique como o ReachView irá se comportar quando a memória estiver cheia, aqui ele pode parar de registrar ou substituir logs antigos pelos novos logs. Na maioria dos casos, recomenda-se “rolling logs”.

### Período de divisão de log
Novo arquivo de log será criado a cada N horas, preservando também o log anterior. Essa configuração permite controlar o tamanho dos arquivos com os quais você trabalha.
