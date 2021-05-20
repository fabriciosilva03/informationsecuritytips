##   Hashes e Senhas - Windows

Introdução: Hashes em Windows

**SAM - Security Account Manager (Windows)**

Armazena as contas de usuários

%SystemRoot%/system32/config/sam

**NTDS.DIT (Windows Server / Active Directory)**

Armazena dados do AD incluindo as contas de usuários

%SystemRoot%/ntds/ntds.dit

**SYSTEM**

Arquivo do sistema necessário para decriptar o SAM/NTDS.DIT

%SystemRoot%/system32/config/system

Obs: Os arquivos acima são protegidos quando estão em execução, ou seja você não consegue copia-los quando estiverem em uso.

**Possivel solução para acesso aos arquivos**

**LOCALMENTE**

Acesso fisico ao computador? Realizar boot com live cd e capturar os arquivos.

**REMOTAMENTE**

C:\Windows\repair (apanesa sistema antigos como XP/2003)

Salvar direo do registro do windows (Desde versões antigas a versões recentes)

Ex: reg save hklm\sam

Cópia somnbra do volume (Versões mais recentes)

Ex: vssadmin


**ATAQUE**

Obter os arquvios e usá-los para obter os hashes

Tentar descobrir os hashes obtidos

**OUTRAS TÈCNICAS**

Senhas em memória/cache - Utilizar técnicas para obter senhas em cache ou na memória do Sistema.

Pass The Hash - Técnica para utilizar um hash sem precisar quebrá-lo

Captura de hashes na rede

**Exemplo de Hashes no Windows**

**Usuário   ID    LM(LAN MANAGER)   -   NTLM(NT LAN MANAGER)**

Administrador:500:aa.......................ee:ae..........................:::

rafaela:1005:aa...........................ee == vazio (significa que não está usando LM então se torna mais fácil de quebrar.)

Obs: ID = 500 - Corresponde a uma conta de administrador.

