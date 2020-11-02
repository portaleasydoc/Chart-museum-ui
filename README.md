# chart-museum-ui
Chart museum en docker-compose con interfaz de usuario

## Install Helm push para helm3

-   Vamos a instalar el plugin de push para helm, para poder subir nuestros charts a nuestro repositorio.
```
$ helm plugin install https://github.com/chartmuseum/helm-push.git
```
-   Ahora si ejecutamos el comando helm para ver las opciones veremos que push se encuentra entre los comandos que podemos ejecutar.
 
## Install Chart-museum docker-compose
-   Vamos a levantar nuestro proyecto de docker-compose.yml
```
$ docker-compose up -d
```
## Add Repositorio local 
- Ejecutamos en nuestra máquina:
```
$ helm repo add chartmuseum http://localhost:8080
```
-   Veremos con un ``` $ helm repo list ``` nuestro repositorio local.
## Push de un Chart de helm
-   Creamos un chart de prueba con:
```
$ helm create test
```
-   Hacemos push de este chart de prueba que acabamos de crear.
```
$ helm push test chartmuseum
```
### Notas
-   Si accedemos por el puerto 80 (o por el puerto por el que lo hemos redirigido en nuestro docker-compose), accederemos a la interfaz gráfica de chart-muiseum.
-   El proyecto original se encuentra en https://github.com/chartmuseum/ui