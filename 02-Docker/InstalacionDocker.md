Instalación de Programas

Docker Sirve para empaquetar y unificar una aplicación sin necesidad de instalarse miles de programas que use cada tecnología de la aplicación.

- Docker Engine in Ubuntu

- Docker Compose

Documentación Oficial de descarga: [Docker Engine overview | Docker Documentation](https://docs.docker.com/engine/)

**Comandos de instalación para una distribución basada en ubuntu**

```
sudo apt-get update
```

```
sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo apt-key fingerprint 0EBFCD88
```

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```

```
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

```
sudo service docker status
```

**Configuración e instalación de docker compose**

sudo groupadd docker

sudo usermod -aG docker ${USER}

curl -L "https://github.com/docker/compose/releases/download/1.28.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

chmod +x /usr/local/bin/docker-compose

sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

docker-compose --version

**Descargar la imagen billingapp**

docker pull juandieruiz/devops:0.0.1

**Crear el contenedor billingapp**

docker run -p 80:80 -p 8080:8080 --name billingapp juandieruiz/devops:0.0.1

**Listar los contenedores existentes**

docker ps -a

**Detener un contenedor**

docker stop nombreobjeto

**Ver los logs de un contenedor**

docker logs nombreobjeto

**Iniciar un contenedor detenido**

docker start nombreobjeto

**Listar las imagenes locales**

docker image ls

**Eliminar una imagen**

docker image rm nombreobjeto

**Descargar las imagenes usando docker-compose**

docker-compose -f stackdb.yml pull

**Iniciar los contenedores**

docker-compose -f stackdb.yml up -d

**Url de la interface de adminer**

[http://localhost:9090/](http://localhost:9090/) **Construir la imagen**

docker build -t billingapp:prod --no-cache --build-arg JAR_FILE=target/*.jar .

**Levantar el contendor para probar**

docker run -p 80:80 -p 8080:8080 --name billingapp billingapp:prod

**Darle un nuevo tag**

docker tag billingapp:prod sotobotero/udemy-devops:0.0.2

**loguearse en el docker engine hacia docker hub**

docker login (usas tu usario y contraseña)

**hacer un push de la imagen**

docker push juandieruiz/devops:0.0.2
