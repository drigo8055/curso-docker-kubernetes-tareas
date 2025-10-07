# 🐬 Despliegue de Servidor MySQL con Docker

Este documento describe los pasos para ejecutar un contenedor con **MySQL** utilizando la imagen oficial de Docker.

---

## 🚀 1. Desplegar el contenedor MySQL

Ejecuta el siguiente comando para iniciar el contenedor:

```bash
docker run -d   --name mi-mysql   -e MYSQL_ROOT_PASSWORD=mi-password-seguro   -p 3306:3306   mysql
```

**Parámetros:**
- `-d`: Ejecuta el contenedor en segundo plano.  
- `--name mi-mysql`: Nombre asignado al contenedor.  
- `-e MYSQL_ROOT_PASSWORD=mi-password-seguro`: Define la contraseña del usuario `root`.  
- `-p 3306:3306`: Expone el puerto MySQL hacia el host.  
- `mysql`: Imagen oficial de MySQL (última versión estable).

---

## 🔍 2. Verificar que el contenedor está en ejecución

```bash
docker ps
```

Deberías ver una salida similar a:

```
CONTAINER ID   IMAGE    COMMAND                  STATUS         PORTS                    NAMES
abcd1234       mysql    "docker-entrypoint.s…"   Up 10 seconds  0.0.0.0:3306->3306/tcp   mi-mysql
```

---

## 🧾 3. Revisar los logs de MySQL

Para confirmar que el servidor MySQL inició correctamente:

```bash
docker logs mi-mysql
```

Busca líneas como:

```
[Server] ready for connections. Version: '8.x.x'  port: 3306
```
## 🛑 4. Detener el contenedor

Para detener el servidor MySQL:

```bash
docker stop mi-mysql
```

---

## 🗑️ 5. Eliminar el contenedor

Para eliminar completamente el contenedor detenido:

```bash
docker rm mi-mysql
```

Verifica que fue eliminado:

```bash
docker ps -a
```
