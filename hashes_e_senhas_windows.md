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


