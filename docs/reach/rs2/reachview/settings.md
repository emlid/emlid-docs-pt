<p style="text-align:center" ><img src="../img/reachview/settings/settings.png" style="width: 800px;" /></p>

## Atualizações do ReachView

### Versão do aplicativo  
Sempre que você liga o Reach em uma rede Wi-Fi, ele verifica se há uma nova atualização do ReachView e o notifica.

!!! note ""
    A verificaação da atualização é feita apenas uma vez durante o processo de inicialização. Se você deseja forçar a verificação de nova versão, vá para o ReachView Updater. Está disponível na porta 5000, por exemplo, `http://reach.local:5000`. O Updater verifica automaticamente os servidores de atualização do Emlid quando você o abre. [Saiba mais sobre o atualizador ReachView.](../common/reachview/updater.md)

## Utilizades do sistema

### Modo noturno 
O modo noturno permite desligar os LEDs até a próxima reinicialização do dispositivo.

### Configurações do conector inferior
Ativa a inicialização automática usando o conector inferior no Reach. Perfeito para integrar o receptor a carros ou tratores.

### Relatório do sistema
A ferramenta é usada para facilitar os relatórios de problemas. Existem dois tipos de relatórios do sistema:

* Relatório simples do sistema (em formato de texto sem formatação)
* Relatório completo do sistema (em um arquivo zip)

O priemiro é para o fórum e facilita o compatilhamento de configurações, estado da rede e versão do aplicativo. O último é para casos mais difíceis e contém registros do sistema e detalhes técnicos do seu dispositivo.

!!! note "Obtendo relatório do sistema"
	<p style="text-align:center"><img src="../img/reachview/settings/system-report.gif" style="width: 800px;" /></p>

### Notificações sonoras

Ativa notificações sonoras no Reach e permite o ajuste de volume. O Reach avisará quando você obtiver ou perder o estado da solução de correção.

### Redefinir as configurações para o padrão  
Clique no botão *Reset setting to default* para retornar todas as configurações à configuração de fábrica. Somente logs e configurações de rede são preservados. Se você deseja executar uma redefinição de fábrica completa e limpar todos os seus dados, pode fazer o processo de [reflash firmware image](../common/reachview/firmware-reflashing.md).

## Configurações gerais

### Nome do Reach e do hotspot (ponto de acesso)

O nome do Reach pode ser alterado para distinguir entre vários dispositivos. Um padrão muito comum é nomear dispositivos de acordo com a sua função, base ou rover. O nome adotado para o dispositivo servirá de base para o nome do ponto de acesso e o nome da rede local. O nome padrão é **reach**, alterando-o também afetará o nome local `http://reach.local` e o nome do ponto de acesso `reach:xx:xx`.

### Configuração de logging
Especifique como o ReachView lidará com o comportamento da memória completa aqui, ele pode parar o log ou substituir os logs antigos em favor dos novos. Na maioria dos casos, recomenda-se “rolling logs”.

### Período de divisão do Log
Um novo arquivo de log será criado a cada N horas, preservando também o log anterior. Essa configuração permite controlar o tamanho dos arquivos com os quais você trabalha.
