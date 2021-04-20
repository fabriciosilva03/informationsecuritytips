# informationsecuritytips
Este repositório contem dicas de segurança da informação, que foram coletadas durante meus estudos!

:compass:	**GUIA DE ESTUDOS**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/guiadeestudos.md"> Guia de Estudos</a>

:cd:	 **VIRTUAL MACHINES | ISOs**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/virtualmachines.md">Virtual Machines</a>


:books:	 **LEITURA:**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/Articles.md"> Artigos </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/write-ups.md"> Write-Ups </a>

:mosquito:	**VULNERABILIDADES:**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/localfileinclusion.md">LFI</a>

:computer: **SCRIPTS**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/scripts.md">Scripts</a>

:hammer_and_wrench: **TOOLS**

**Canivete Suiço:**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/swissarmyknife.md"> Swiss Army Knife </a>

**Conversores:**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/conversores.md"> Conversores </a>


**Redes:**

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/tcpdump.md"> TCPDump </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/wireshark.md"> Wireshark </a>

<a href="https://github.com/fabriciosilva03/informationsecuritytips/blob/main/redes.md"> Redes </a>



## **Terminal Linux**

##### __________________________________________________

##### INTRODUÇÂO: 

##### __________________________________________________

pwd : Lista o endereço do seu diretorio atual.

cd..: Retorna pra um diretorio anterior.

cd {diretorio} : Comando utilizado para acessar um determinado diretorio.

mkdir {nomedodiretorio} : Comando utilizado para criar um diretorio.

touch {nomedoarquivo} : Comando utilizado para criar um arquivo.

touch .arquivo  : Comando para criar um arquivo oculto.

'> {nomedoarquivo}  : Comando utilizado para criar um arquivo.
 
ls  : Lista arquivos contidos no diretorio atual.

ls -l : Comando para listar arquivos e detalhes importantes sobre o mesmo.

ls -la : Lista todos os arquivos visiveis e ocultos.

echo {mensagem} : Imprime uma mensagem.

echo {mensagem} > {arquivo} : Inserindo mensgem em um arquivo substituindo qualquer informação contida no mesmo.

echo {mensagem} >> {arquivo} : Inserindo mensgem em um arquivo de forma a acrescentar caso ja tenha informações contidas no mesmo.

cat : exibe as informações contidas em um arquivo.

tac : exibe informações contidas no arquivo so que forma inversa, ou seja mudando a ordem de apresentação padrão.

head {arquivo}  : Exibe informações somente do cabeçalho do arquivo, ou seja somente da parte superior caso o documento seja muito extenso.

head {arquivo}  -n1 : Exibe informações somente do cabeçalho, e somente da primeira linha.

tail {arquivo}  : Exibe apenas informações do rodapé do arquivo.

tail {arquivo} -n1 : Exibe apenas informações do rodapé do arquivo, e somente da ultima linha.

tail -f {arquivo}  : Exibe informações do arquivo em tempo real, mesmo se alguem estiver alterando algo no mesmo sera possivel visualizar.

cp arquivo1 arquivo2 : Faz a copia de um arquivo.

##### __________________________________________________

##### GERENCIAMENTO DE USUÁRIO:

##### __________________________________________________

adduser {usuario} : Adicionando usuário.

deluser {usuario} : Excluindo usuario.

useradd -d {diretorio} -s /bin/bash {usuario: Adicionado usuário de uma forma mais controlada.

passwd {usuario}  : Adicionando senha ao usuário.

su {usuario} : Acessando via terminal através um outro usuário.

adduser {usuario} sudo : Adicionado o usuario ao grupo sudo.

deluser {usuario} sudo : Excluindo o usuário do grupo sudo.

nano /etc/sudoers : Alterando tais configurações você pode dar permições de root a um usuário especifico.


##### __________________________________________________

##### GERENCIAMENTO DE REDES:

##### __________________________________________________

ifconfig : Exibe informações sobre as configurações da sua rede.

ifconfig eth0 x.x.x.x netmask x.x.x.x : Alterando ip e mascara de sub rede, temporariamente, pois ao reinciar a maquina as configurações padrões se reestabelecem.

nano /etc/network/interfaces : Alterando as configurações deste arquivo pode ficar de forma permanete as alterações de IP e Mascara de sub rede.

route : Mostra a tabela de roteamento.

route add del default : Remove a rota predefinida.

route add default gw x.x.x.x : Adiciona uma nova rota.

netstat -lt : Lista conexoes abertas via TCP.

netstat -lnt : Lista conexoes abertas via TCP e a porta utilizada.

netstat -lntp : Lista conexoes abertas via TCP e a porta utilizada e o nome do programa.

netstat -lu : Lista conexoes abertas via UDP.

##### __________________________________________________

##### EDITOR DE TEXTO:

##### __________________________________________________

nano {nomearquivo} : Criar e abre o arquivo para ser editado via editor nano.
Exemplo de atalho no editor nano:
Ctrl + x : Exit

vi {nomearquivo} : Abre arquivo para ser editado via editor vi.

Exemplo de buscar algo no vi:
Esc 
/nomebuscado.

Exemplos de comandos Vi:
Esc
:q  : Sair do editor
:q! : Força a sair sem salvar
:wq : Salva o arquivo e sai do editor.

leafpad : Editor de texto simples em modo gráfico.

##### __________________________________________________

##### PACOTES:

##### __________________________________________________

/etc/apt/sources.list : Este arquivo contem a lista de repositorios de download de pacotes do sitema.

apt update : Comando para atualizar o sistema.

apt upgrade : Instala as atualizações baixadas.

apt search {pacote} : busca por algumas aplicação disponivel no meu repositorio.

apt install {pacote} : instala aplicação no meu sistema.

apt remove {pacote} : removendo pacote.

dpkg -i {arquivo.deb} : comando para instalar pacotes .deb

dpkg -l : lista pacotes dpkg instalados no sistema.


##### __________________________________________________

##### SERVIÇOS:

##### __________________________________________________

service {serviço} start : iniciando o serviço.

service {serviço} stop : Parando o serviço.

service {serviço} restart : Reiniciando o serviço.

update-rc.d {serviço} enable : Comando para fixar um serviço, ou seja mesmo que a maquina seja reiniciada o serviço ira inciar de forma automática.

update-rc.d {serviço} disable : Comando para desabilitar a incialização de serviços extras ao inciar a maquina.

reboot : reinciar o sistema

poweroff : comando para desligar o sistema.

##### __________________________________________________

##### ARQUIVOS:

##### __________________________________________________

locate {arquivo} : comando para localizar o arquivo.

updatedb : comando para atulizar os dados do sistema e o comando locate buscar arquivos criados recentemente.

whereis {aplicação} : Buscando aplicações no sistema. Ex: whereis {nmap}

find /caminho/ -name {nomedoarquivo} : comando de busca por diretorio especifico e por nome do arquivo. Ex: find /home/ -name artigo.doc

find / -name {nomedoarquivo} : comando de busca em todos os  diretorios do sistema.

##### __________________________________________________

##### GANHANDO TEMPO:

##### __________________________________________________

**GREP** 

##### Buscando por linhas que contenham um trecho de especifico:

Ex: cat /dir/arquivo | grep "termpobuscado"

Ex2: grep "termpobuscado" /dir/arquivo 

##### Buscando por linhas que contenham um trecho de especifico e armazenando dentro de um arquivo.

Ex2: grep "termpobuscado" /dir/arquivo > arquivo2

##### Buscando por linhas que não contenham um trecho de especifico:

Ex2: grep -v "termpobuscado" /dir/arquivo


**EGREP**
##### Buscando por linhas que não contenham um mais de um trecho de especifico:

Ex2: grep -v "termpobuscado|termpobuscado2" /dir/arquivo


**AWK**
##### Exibindo apenas partes por coluna especifica.

Ex: awk -F : '{print $1}' arquivo

Ex2: awk -F : '{print $1,$6}' arquivo


**CUT**
#####  Exibe informações apartir de delimitadores

Ex: cut -d : -f1 arquivo

Ex: cut -d : -f1,6 arquivo

Ex: cut -d : -f1-6 arquivo


**SED**
##### Utilizado para auxiliar no processo de alteração de multiplos dados de um arquivo.

Ex: sed 's/palavrax/palavray/' arquivo


##### __________________________________________________

##### TOOLS KALI:

##### __________________________________________________

**Quebrar senhas:**

hashcat -m0 hash.txt passlist.txt

john --format=raw-md5 "Nome do arquivo que contém a hash ou as hashes" --wordlist="Diretório onde a sua lista com possíveis senhas está".

**Web shell**

weevely generate {senhadeacesso} {nomedabackdoor.extesão}

**Convertendo dados hexadecimais**

Ex:

printf "%d\n" 0x....

Ex2:

printf "%d.%d.%d.%d\n" 0x.. 0x... 0x... 0x...

**Listando os codigos de cada tipo de protocolo**

cat /etc/protocols

**Manual da tabela ascii**

man ascii

**Convertendo dados da tabela ascii**

Ex:

printf "\x..\x..\x..\x..\x..\x..\n" 


**TCPDUMP:**

**Capturando trafego**

tcpdump -vnw {arquivo}.pcap

**Leitura do trafego capturado.**

tcpdump -vnr {arquivo}.pcap

**Leitura filtrada por porta:**

tcpdump -vnr {arquivo}.pcap port 21


**O COMANDO WC**

Este comando é utilizado para contar caracteres, palavras e/ou linhas dos dados da entrada padrão e apresenta o resultado na saída padrão.

-l: conta as linhas;

-w: conta as palavras;

-c: conta os caracteres.

Exemplos:

**wc -l texto.txt**

26 texto.txt

**wc -w texto.txt**

14 texto.txt

**wc texto.txt**

2346   282   26







 





