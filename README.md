# Práctica: Automatización de Infraestructura con Terraform y Ansible

## 1. Introducción

En esta práctica se pone en marcha un flujo completo de infraestructura como código (IaC), utilizando las herramientas Terraform y Ansible para desplegar y configurar una máquina virtual Ubuntu 24.04 sobre VirtualBox.

Terraform se encarga de la creación de la máquina virtual, asignando los recursos necesarios como CPU, memoria, red y disco, mientras que Ansible se ocupa de la configuración del sistema operativo una vez provisionado: actualización de paquetes, instalación del servidor web Apache y despliegue de una página personalizada accesible vía navegador.

Este enfoque permite construir entornos reproducibles y estandarizados, facilitando la gestión de sistemas a través de automatización, algo esencial en entornos modernos de desarrollo y operaciones (DevOps).

## 2. Objetivos

1. Provisionar una máquina virtual Ubuntu 24.04 en VirtualBox mediante Terraform.

2. Configurar la máquina con Ansible a través de SSH.

3. Automatizar la instalación de Apache y la creación de una página web personalizada.

4. Verificar el funcionamiento del servidor web de forma automática.

## 3. Herramientas utilizadas

1. Terraform (v1.x)

2. Ansible (v2.15 o superior)

3. VirtualBox (v7.x)

4. Ubuntu Desktop 24.04 (host de Ansible)

5. Ubuntu Server 24.04 (máquina virtual provisionada)

## 4. Conclusión

La práctica ha permitido comprobar cómo las herramientas de infraestructura como código pueden automatizar tanto el aprovisionamiento como la configuración de sistemas, desde la creación de máquinas virtuales hasta la instalación y verificación de servicios.

Gracias al uso combinado de Terraform y Ansible, se consigue una solución robusta, eficiente y replicable, alineada con las mejores prácticas de automatización en entornos DevOps.

Este tipo de enfoque resulta especialmente útil para crear laboratorios, entornos de pruebas o incluso entornos de producción en entornos controlados, reduciendo errores manuales y acelerando el ciclo de despliegue.