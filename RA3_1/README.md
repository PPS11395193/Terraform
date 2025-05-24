# 1. Creación de una máquina virtual Ubuntu 24.04 con Terraform en VirtualBox

En este apartado se explica cómo desplegar una máquina virtual con Ubuntu 24.04 usando Terraform como herramienta de automatización y VirtualBox como plataforma de virtualización.

Terraform permite definir y automatizar tanto la creación como la configuración inicial de la máquina virtual, incluyendo aspectos como:

1. Asignación del nombre y selección del sistema operativo.

2. Definición de recursos hardware (CPU, RAM y almacenamiento).

3. Configuración de la red (NAT, puente, etc.).

4. Registro automático e inicio de la VM.

Este procedimiento proporciona entornos consistentes y reproducibles, lo cual facilita su integración con otras herramientas como Ansible para tareas de configuración del sistema y despliegue de servicios o aplicaciones.

A continuación, se muestra un ejemplo básico del archivo main.tf utilizado para este despliegue:

``` bash
terraform {
  required_providers {
    virtualbox = {
      source  = "shekeriev/virtualbox"
      version = "0.0.4"
    }
  }
}

provider "virtualbox" {}

resource "virtualbox_vm" "ubuntu_2404" {
  name   = "PPS_RA5_2_ubuntu-24.04"
  image  = "https://vagrantcloud.com/generic/ubuntu2404/versions/2.1.26/providers/virtualbox.box"
  cpus   = 2
  memory = "2048 mib"

  network_adapter {
    type   = "nat"
    device = "IntelPro1000MTDesktop"
  }
}
```

Para organizar el proyecto, se ha creado una carpeta específica destinada a los archivos de Terraform que componen la infraestructura a desplegar.

Con el archivo main.tf listo, se abre una consola de comandos en Windows y se ejecuta el siguiente comando para inicializar el entorno:

``` bash 
terraform init
```

![init](https://github.com/PPS11395193/Terraform/tree/main/img/Captura1.jpg)

Tras la inicialización, se puede ejecutar:

``` bash 
terraform plan
```

![plan](https://github.com/PPS11395193/Terraform/tree/main/img/Captura2.jpg)

Este comando muestra un resumen detallado de las acciones que Terraform realizará para crear la máquina virtual.

Verificado el plan, se continúa con el despliegue ejecutando:

![apply](https://github.com/PPS11395193/Terraform/tree/main/img/Captura3.jpg)

Una vez completado el proceso, se puede comprobar en VirtualBox que la VM se ha creado correctamente, está configurada según lo definido y ha sido iniciada automáticamente.

![VM](https://github.com/PPS11395193/Terraform/tree/main/img/Captura4.jpg)