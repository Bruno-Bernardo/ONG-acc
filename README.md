# ONG-acc
Instale NGINX
```
sudo apt install nginx
```
Após instalado basta acessar localhost pelo seu navegador para verificar se o nginx está funcionando corretamente

Em seguida altere o arquivo **/etc/nginxsites-available/default** modificando a localização dos arquivos do site para a pasta aonde encontra-se este projeto, exemplo:
```
server {
	listen 80 default_server;
	listen [::]:80 default_server;

  #Altere este caminho
	root /home/user/ONG-acc;

	index index.html index.htm index.nginx-debian.html;

	server_name _;

	location / {
		try_files $uri $uri/ =404;
	}
}
```
Após o nginx ser modificado reinicie o mesmo com o seguinte comando 
```
service nginx restart
```
