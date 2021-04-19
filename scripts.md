**BASH SCRIPTING - LINUX**

SCAN DE PORTAS: 

```
#!/bin/bash

#Scaneado de portas.

if ["1$" == ""]
	then
    
    #echo "Digite o argumento conforme o exemplo:"
		#echo "Exemplo:" 
    #echo "./script 192.168.0.1"
    
	else
		for p in {1..100};do
		hping3 -S -p $p $1 -c 1 | grep "SA" | grep -v "RA" >> list_port
		clear
		cat list_port		
		
done
fi
```

SCANEAMENTO DE SUBDOMINIO:

```
#!/bin/bash
    
    #echo "Digite o argumento conforme o exemplo:"
		#echo "Exemplo:" 
    #echo "./script 192.168.0.1"

if ["1$" == ""]
	then
		echo "Digite o argumento de forma correta"
	else
		wget $1 
		clear
	cat index.html | grep "http" | cut -d "/" -f 3 | cut -d '"' -f 1 > lista
	while read line; do 
	host  "$line"; 
	done < lista	
	rm -f index.html

fi

```

**POWER SHELL**




**LINGUAGEM C**




**PYTHON**
