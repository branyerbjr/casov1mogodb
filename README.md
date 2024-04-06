# CASO V1 DOCKER

### Crear la red
- docker network create casov1-red
### Construir las imagenes
- docker build -t casov1 .
- docker build -t casov1mongo -f Dockerfile-mongo .
### Desplegar Contenedores
- docker run  -d -p 4000:3000 --network casov1-red --name web-casov1 casov1
- docker run -d -p 28017:27017 --name mongoaws --network casov1-red casov1mongo
