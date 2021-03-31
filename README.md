# informationsecuritytips
Este repositório contem dicas de segurança da informação, que foram coletadas durante meus estudos!
## **Terminal Linux**

##### __________________________________________________

##### INTRODUÇÂO: 

##### __________________________________________________

##### pwd : Lista o endereço do seu diretorio atual.
##### cd..: Retorna pra um diretorio anterior.
##### cd {diretorio} : Comando utilizado para acessar um determinado diretorio.
##### mkdir {nomedodiretorio} : Comando utilizado para criar um diretorio.
##### touch {nomedoarquivo} : Comando utilizado para criar um arquivo.
##### touch .arquivo  : Comando para criar um arquivo oculto.
##### > {nomedoarquivo}  : Comando utilizado para criar um arquivo.
##### ls  : Lista arquivos contidos no diretorio atual.
##### ls -l : Comando para listar arquivos e detalhes importantes sobre o mesmo.
##### ls -la : Lista todos os arquivos visiveis e ocultos.
##### echo {mensagem} : Imprime uma mensagem.
##### echo {mensagem} > {arquivo} : Inserindo mensgem em um arquivo substituindo qualquer informação contida no mesmo.
##### echo {mensagem} >> {arquivo} : Inserindo mensgem em um arquivo de forma a acrescentar caso ja tenha informações contidas no mesmo.
##### cat : exibe as informações contidas em um arquivo.
##### tac : exibe informações contidas no arquivo so que forma inversa, ou seja mudando a ordem de apresentação padrão.
##### head {arquivo}  : Exibe informações somente do cabeçalho do arquivo, ou seja somente da parte superior caso o documento seja muito extenso.
##### head {arquivo}  -n1 : Exibe informações somente do cabeçalho, e somente da primeira linha.
##### tail {arquivo}  : Exibe apenas informações do rodapé do arquivo.
##### tail {arquivo} -n1 : Exibe apenas informações do rodapé do arquivo, e somente da ultima linha.
##### tail -f {arquivo}  : Exibe informações do arquivo em tempo real, mesmo se alguem estiver alterando algo no mesmo sera possivel visualizar.
##### cp arquivo1 arquivo2 : Faz a copia de um arquivo.

##### __________________________________________________

##### GERENCIAMENTO DE USUÁRIO:

##### __________________________________________________

##### adduser {usuario} : Adicionando usuário.
##### deluser {usuario} : Excluindo usuario.
##### useradd -d {diretorio} -s /bin/bash {usuario: Adicionado usuário de uma forma mais controlada.
##### passwd {usuario}  : Adicionando senha ao usuário.
##### su {usuario} : Acessando via terminal através um outro usuário.
##### adduser {usuario} sudo : Adicionado o usuario ao grupo sudo.
##### deluser {usuario} sudo : Excluindo o usuário do grupo sudo.
##### nano /etc/sudoers : Alterando tais configurações você pode dar permições de root a um usuário especifico.









 





