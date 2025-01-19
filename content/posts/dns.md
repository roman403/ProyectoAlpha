---
title: "DNS"
date: 2025-01-18T13:11:55+01:00
# bookComments: false
# bookSearchExclude: false
---
Aquí tienes el texto en formato Markdown, incluyendo indicaciones para las imágenes: 

```markdown
# Configuración de DNS en AWS

## Paso 1: Crear las máquinas en AWS

Creamos las máquinas en AWS y usamos la contraseña generada para conectarnos mediante acceso remoto de Windows. Usamos el usuario `Administrator` y la IP pública de la máquina.

**Sistema Operativo:** Windows Server 2022

![Conexión remota](docs/imagenes/dns1.png)

---

## Paso 2: Instalación del DNS

Una vez conectados, instalamos el servicio DNS desde **Roles y Características**.

![Instalación de DNS](docs/imagenes/dns2.png)

---

## Paso 3: Acceso a Herramientas Administrativas

Nos dirigimos a **Herramientas Administrativas** y seleccionamos **DNS**.

![Herramientas Administrativas - DNS](docs/imagenes/dns3.png)

---

## Paso 4: Crear una zona primaria

Creamos una **Zona Nueva Primaria**.

![Crear zona primaria](rudocs/imagenes/dns4.png)

---

## Paso 5: Configurar el dominio

Configuramos el dominio deseado.

![Configuración del dominio](docs/imagenes/dns5.png)

---

## Paso 6: Crear alias para las máquinas

Creamos 4 alias que representarán las máquinas que usaremos en el reto (utilizando las IPs privadas).

![Crear alias](docs/imagenes/dns6.png)

---

## Paso 7: Configurar un servidor secundario

Añadimos un servidor secundario, configurado para realizar la transferencia solo a dicho equipo por motivos de seguridad. Este servidor será una máquina con **Ubuntu 24**.

![Configuración del servidor secundario](docs/imagenes/dns7.png)

---

## Paso 8: Cambiar el DNS de la máquina primaria y realizar comprobaciones

Modificamos la configuración del DNS en la máquina primaria y realizamos una comprobación para validar los cambios.

![Cambio y comprobación del DNS](docs/imagenes/dns8.png)

---

## Paso 9: Configuración del servidor secundario

1. Nos conectamos a la máquina secundaria, que será un servidor con **Ubuntu 24**.
2. Cambiamos la configuración del DNS, apuntando a la IP de la máquina primaria.
3. Instalamos el servicio DNS en Ubuntu.

