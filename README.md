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


## COMANDOS DE DESPLIEGUE
- DOCKER

docker pull nmatsui/hello-world-api
docker run -d --rm -p 3000:3000 nmatsui/hello-world-api



## Arquitectura y Servicios

- **app1**: API Node.js - Puerto `3000:3000`
- **app2**: API Node.js - Puerto `3001:3000`
- **app3**: API Node.js - Puerto `3002:3000`
- **db**: PostgreSQL 13 - Puerto `5432:5432` con volumen persistente `db_data`

---

## Variables de Entorno

El proyecto desacopla la configuración mediante un archivo `.env` local (ignorado por Git). Se provee la plantilla `.env.example`:

| Variable | Descripción | Valor de Ejemplo |
| :--- | :--- | :--- |
| `MESSAGE` | Mensaje devuelto por los endpoints de las réplicas | `"Bienvenida, Estudiante"` |
| `POSTGRES_USER` | Usuario de base de datos | `user` |
| `POSTGRES_PASSWORD` | Contraseña de PostgreSQL | `password` |
| `POSTGRES_DB` | Nombre de la base de datos | `mydatabase` |

---

## Instrucciones de Despliegue

### 1. Configurar variables de entorno
Copiar el archivo de plantilla y definir las variables:
```bash
cp .env.example .env