---
title: "Nginx"
date: 2025-01-18T13:12:22+01:00
# bookComments: false
# bookSearchExclude: false
---
Esto es la documentacion de Nginx

Aquí te paso el contenido que mencionaste en formato Markdown (.md) hasta el punto de "Conexión segura":

```markdown
# REDHAT S.O.

Hemos elegido varios S.O. cada uno centrado en una tarea para un mejor rendimiento y una mayor redundancia. Así evitamos que si una máquina se cae, sea lo que perjudique a varios servicios a la vez.

## REDHAT

Lo lanzamos con AWS. La configuración por ahora será la default y le iremos modificando mientras progresa el proyecto.

## Servicios

### Nginx

#### Instalación

La instalación de Nginx será en la máquina de **REDHAT**.  
Nos conectamos a la máquina mediante SSH.  
Ahora, con el comando `yum` y con los permisos de `sudo`, instalamos Nginx:

```bash
sudo yum install nginx
```

Le damos a **y** (sí).

#### Configuración

1. Primero, iniciamos el servicio de Nginx con el comando `start`:

    ```bash
    sudo systemctl start nginx
    ```

2. Luego habilitamos el inicio automático cada vez que se inicie el sistema:

    ```bash
    sudo systemctl enable nginx
    ```

3. Ahora, si hacemos un `status`, veremos que el servidor está encendido:

    ```bash
    sudo systemctl status nginx
    ```

4. Para que todo el mundo pueda acceder, habilitamos en las reglas de entrada el puerto 80:

    ```bash
    sudo firewall-cmd --zone=public --add-port=80/tcp --permanent
    sudo firewall-cmd --reload
    ```

5. Al ser un servidor que sirve a la red, le decimos que escuche para todas las IP y en cualquier red.  
   Al buscar nuestra IP, nos toparemos con la página predeterminada de Nginx.

6. Editamos el fichero de configuración de Nginx del virtual host **sin TLS**.

#### Archivos HTML

Los enviamos con el comando `scp`:

```bash
scp -r /ruta/a/archivos usuario@ip_destino:/ruta/de/destino
```

Instalamos la herramienta **zip**:

```bash
sudo yum install zip
```

Ahora, moveremos las carpetas que necesitemos, en este caso son todas menos las carpetas **empresa** y **ventas**.

Una vez los tenemos, ya funcionará la configuración de Nginx.

#### Cambiar propietario y grupo

Para cambiar el propietario y el grupo propietario, usamos el siguiente comando:

```bash
sudo chown -R usuario:grupo /ruta/del/directorio
```

#### Cambiar privilegios

Finalmente, cambiamos los privilegios necesarios para los archivos:

```bash
sudo chmod -R 755 /ruta/del/directorio
```

```
