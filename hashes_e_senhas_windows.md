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





