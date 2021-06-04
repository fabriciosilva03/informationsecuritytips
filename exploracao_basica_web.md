## Exploração básica (Web)

## Git Exposed Attack

LAB: Git Exposed

Plugin Browser: DotGit - Pluguin para detectar se existe uma pasta .git na apalicacação web.

Uma ferramenta para despejar um repositório git de um site:

https://github.com/arthaud/git-dumper

Comands: 

`wfuzz -c -z file,common.txt --hc 404 --hh 264 http://192.168.0.1/FUZZ`

`python3 git_dumper.py http://192.168.0.1/ info_git`

`git status`

`git log`

`git show`



