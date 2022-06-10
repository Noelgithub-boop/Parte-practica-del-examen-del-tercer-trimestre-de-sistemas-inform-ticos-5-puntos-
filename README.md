# Parte-practica-del-examen-del-tercer-trimestre-de-sistemas-inform-ticos-5-puntos-

## 1- Introducción
Lo primero que debemos tener en cuenta al realizar esta actividad es que tenemos que tener tanto instalados el Docker engine  ,como el servidor tomcat ..etc en mi caso tomcat 9.0 ya que su última version da muchos errores.

Dependiendo de nuestro SO , deberemos instalar docker ,en caso de Linux con el  el correspondiente comando  o, en mi caso en una maquina windows instalando " Docker Desktop "


## 2- Configuración del archivo docker-compose.yml

Para configurar el docker-compose.yml , deberemos tener instalado el "docker-compose", una de las ventajas que tendremos al instalar Docker Desktop en Windows es que el Docker compose viene incluido en el paquete de instalación.
Seguido esto procedemos a la configuración del archivo docker-compose.yml.
En el siguiente archivo he recopilado todos las configuraciones Docker-Compose que hay que realizar.
Tanto la configuración de  la base de datos (db),la configuración de phpmyadmin(herramienta idónea para la gestión de bases de datos) y la imagen del tomcat ( herramienta usada principalmente para hostear Java Servlets).
![Screenshot_1](https://user-images.githubusercontent.com/91748397/173108316-d319d439-1222-41c0-9a9f-0a75492b8b89.png)

Después de la configuración del Docker Compose podemos proceder al despliegue de la aplicación.

## 3- Pasos para el despliegue de la aplicación

Lo primero que debemos hacer ,tal y  como aprendimos este trimestre a navegar entre ficheros en la consola, es acceder a la carpeta que contiene nuestro trabajo.
![Screenshot_2](https://user-images.githubusercontent.com/91748397/173108999-c32e4904-b00d-49ff-bb16-6d68fca06dc1.png)

Ejecutamos Docker Desktop ( no pondre capturas de esto ya que es un proceso muy simple).
Y procedemos con el primer código * docker-compose up * Este comando , ayuda a construir la imagen , ayudandose de los archivos Docker-compose .yml previamente configurados , creará y lanzará los contenedores Docker con los servicios configurados previamente (paso1)![Screenshot_3](https://user-images.githubusercontent.com/91748397/173110516-90fb24c7-1999-457f-8db4-fae4295da038.png)
Como podemos apreciar se  crean las imagenes : ![Screenshot_4](https://user-images.githubusercontent.com/91748397/173110748-033d4d06-1a39-47ce-8601-adfbf8fac3eb.png)
Sabemos que las tres imágenes han sido creadas correctamente cuando aparezca"done"
![Screenshot_5](https://user-images.githubusercontent.com/91748397/173110993-cd882b45-8529-4dc2-8c02-b8c860555858.png)

## 4- Preparación y subida de la imagen a dockerhub

Podemos comprobar que funciona correctamente , mediante el acceso del LocalHost y la dirección de la carpeta![Screenshot_6](https://user-images.githubusercontent.com/91748397/173111432-d040c17d-8dda-41e7-bc1e-b47d78d44b79.png)
A continuación podemos acceder a phpMyAdmin , mediante los valores previamente especificados en el docker Compose![Screenshot_7](https://user-images.githubusercontent.com/91748397/173111886-361306b9-08c0-4166-a324-12dce5110a78.png)
Podemos confirmar que la base de datos ha sido creada correctamente![Screenshot_8](https://user-images.githubusercontent.com/91748397/173112221-85f2476f-fc7b-4be6-8c9f-e5c10419a8b0.png)
Para evitarnos errores debemos crear una tabla en la base de datos previamente :![Screenshot_9](https://user-images.githubusercontent.com/91748397/173113292-e23fdf87-4063-4625-becf-ba35ac4533d5.png)
Los ultimos pasos es subir la imagen a docker-hub , consiste en unos sencillos pasos , el primero de ellos apagar la imagen actual mediante el comando:![Screenshot_10](https://user-images.githubusercontent.com/91748397/173113996-843bc364-f0ed-4af4-91f1-49cad505e52d.png)

Por ultimo deberemos subir el proyecto al Docker-Hub 
mediante el comando * docker build -t noel9969/nombre_imagen docker-latest .
Nos saldrá esto confirmando que ha sido un exito.![Screenshot_11](https://user-images.githubusercontent.com/91748397/173114878-3112056d-4564-4ed4-b2c2-b2bc62567fb3.png)

Por último hacemos el push de la imagen ![Screenshot_13](https://user-images.githubusercontent.com/91748397/173115090-313087d4-874f-44b3-8685-641cdcb9eb3c.png)
CONFIRMACION DE QUE SE HA SUBIDO LA IMAGEN:
![Screenshot_14](https://user-images.githubusercontent.com/91748397/173115272-b5008dce-a6cb-4cce-b7a7-4e50e0c16566.png)


https://hub.docker.com/

