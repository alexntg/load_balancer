
ejecutamos los comandos para crear los contenedores

sudo docker run --rm -v PATH_TO_index.1.html:/usr/share/nginx/html/index.html -p 8080:80 --name servidor1 nginx
sudo docker run --rm -v PATH_TO_index.2.html:/usr/share/nginx/html/index.html -p 8080:80 --name servidor2 nginx
sudo docker run --rm -v PATH_TO_index.3.html:/usr/share/nginx/html/index.html -p 8080:80 --name servidor3 nginx

inspeccionamos cada contendor para sacar la ip
podemos sacar la ip del primero y sumar 1 para el segundo archivo y sumar 2 a la ip del tercero

docker inspect servidor1
docker inspect servidor2
docker inspect servidor3

buscamos el archivo hosts y lo editamos

[]$ sudo find / -type f -name "hosts"
/etc/hosts
[]$ nano /etc/hosts

le añadimos las ips

172.17.0.4 server3.com
172.17.0.3 server2.com
172.17.0.2 server1.com

y por ultimo buscamos las direcciones en nuestro buscador

http://server1.com/
http://server2.com/
http://server3.com/
