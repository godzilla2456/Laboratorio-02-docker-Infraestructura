# Laboratorio 02 - Docker Compose
## Integrantes 
- Tarazona Aransaenz, Andrea Alejandra

## Preguntas Teóricas

### Tipos de redes de Docker
- **Host**: Comparte la pila de red del anfitrión con el contenedor, se elimina el aislamiento de puertos.
- **Overlay:** Conecta contenedores que se ejecutan en diferentes máquinas o hosts físicos.
- **Bridge:** Sale como predeterminada al crear contenedores en un mismo host. Permite aislarlos y que se comuniquen entre sí mediante IP o nombres del servicio.
- **Macvlan:** Asigna una direccion MAC fisica al contenedor para que figure como un dispositivo fisico independiente en la red loca.
- **None:** Desactiva cualquier interfaz de red del contenedor dejándolo totalmente aislado del exterior. 

###  Tipos de volumen que existen en docker

- **Bind Mounts:** Mapea una carpeta o archivo específico de la máquina local dentro del contenedor. Es útil durante el desarrollo para sincronizar código. 

- **Tmfs:** Almacena información solo en la memoria RAM del host, los datos no tocan el disco y se eliminan al detener el contenedor. 

- **Dejar vacio por el momento, en las páginas que estoy revisando esos dos son los que más se repiten, al finalizar la actividad retornar a este punto**


