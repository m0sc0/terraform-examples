# DESPLIEGUE DE CONTAINER DOCKER NGINX EN INSTANCIA AWS CON TERRAFORM 

El objetivo de este repositorio es mostrar como desplegar autom谩ticamente desde terraform una instancia de AWS que contenga una imagen docker de Nginx.

## Pre-requisitos 馃搵

- TERRAFORM .12 o superior
- AWS CLI
- CUENTA FREE TIER AWS 

## Comenzando 馃殌

1) Instalamos Terrafom https://learn.hashicorp.com/tutorials/terraform/install-cli
2) Creamos cuenta free tier en AWS  https://aws.amazon.com/
3) Instalamos AWS CLI https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html
4) Creamos usuario AWS en la secci贸n IAM con acceso Program谩tico y permisos de administrador https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_create.html   
5) Configuramos el AWS CLI https://docs.aws.amazon.com/polly/latest/dg/setup-aws-cli.html

## Despliegue 馃摝

### Consideraciones iniciales

- Para la realizaci贸n de este despliegue elegimos la imagen AWS Linux 2 montada sobre una instancia t2.micro.
- La instalaci贸n de docker y el container Ngnix dentro de la instancia se realiz贸 a trav茅s de un archivo bash que se carga el user data en la instancia.
- La generaci贸n de la clave de la instancia se realiza con el recurso terraform  tls_private_key  

### Ejecutamos el despliegue

1) Clonamos el repositorio en la carpeta
2) Ejecutamos terraform int, para que terraform baje los plugins necesarios
3) Ejecutamos terraform plan -var aws_access_key=XXXX -var aws_secret_key=XXX -out plan.tfplan
4) Ejecutamos terrafom apply -var aws_access_key=XXXX -var aws_secret_key=XXX para que realice el despliegue.
5) Vamos a muestra cuenta de AWS para verificar que se haya realizado el despliegue
6) Nos conectamos a nuestra instancia y corremos el comando sudo docker ps -a para verificar que el container con la imagen Nginx este corriendo. 
7) Copiamos la ip publica de nuestra instancia y ponemos en nuestro navegador, se mostrar la p谩gina de inicio de Ngnix.

## Informaci贸n de referencia 馃洜锔?

https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-docker/#manage
https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html


