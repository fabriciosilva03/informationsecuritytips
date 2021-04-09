**Wireshark**


**Exemplos de filtros:**

Filtrar por IP de origem:

ip.src==192.168.1.5

 
Filtrar por IP de destino:

ip.dst==192.168.1.7

 
Filtrar por requisições GET do http:

http.request.method == "GET"

 
Filtrar por requisições POST do http:

http.request.method == "POST"

 
Filtrar por GET e POST:

http.request

 
Filtrar pelo host do http:

http.host=="192.168.10.11"

 
Filtrar pela URI:

http.request.uri=="/app/login.xhtml"

 
Filtrar pela porta TCP:

tcp.port==443

 
Filtrar pela porta UDP:

tcp.port==4562



tcp.flags.syn==1 && tcp.flags.ack==0

http.request.method == “POST” && http.host==”192.168.10.11″ && http.request.uri==”/app/login.xhtml”




**Referências:**

Display Filter Reference: Hypertext Transfer Protocol

https://www.wireshark.org/docs/dfref/h/http.html

Reconstruindo arquivos de pacotes Wireshark

https://shankaraman.wordpress.com/tag/how-to-extract-ftp-files-from-wireshark-packet/
