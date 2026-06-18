# Examen Final Arquitectura de Computadores

## Información del estudiante

**Nombre completo:** Laura Michell  Garcia Uribe
**Código estudiantil:** 0192501
**Asignatura:** Arquitectura de Computadores
**Proyecto:** Despliegue automatizado de una instancia EC2 en AWS

---

## Objetivo del proyecto

El objetivo de este proyecto es desplegar una instancia EC2 en AWS utilizando una plantilla de CloudFormation y automatizando el proceso mediante GitHub Actions.

La instancia EC2 configura automáticamente un servidor web por medio de UserData, permitiendo publicar una página HTML con estilos CSS y funcionalidad básica en JavaScript. Esta página contiene el nombre del estudiante, el código estudiantil y el texto requerido: **Examen Final Arquitectura de Computadores**.

---

## Tecnologías utilizadas

* AWS EC2
* AWS CloudFormation
* GitHub Actions
* Git
* GitHub
* Amazon Linux
* Apache HTTP Server
* HTML
* CSS
* JavaScript

---

## Estructura del proyecto

```text
.github/
└── workflows/
    ├── deploy.yml
    └── destroy.yml

template/
└── ec2.yaml

README.md
```

---

## Descripción de los archivos

### deploy.yml

El archivo `deploy.yml` contiene el workflow de GitHub Actions encargado de realizar el despliegue de la infraestructura en AWS.

Este workflow realiza las siguientes acciones:

1. Descarga el contenido del repositorio.
2. Configura las credenciales de AWS mediante GitHub Secrets.
3. Valida la plantilla de CloudFormation.
4. Despliega el stack en AWS.

---

### destroy.yml

El archivo `destroy.yml` contiene el workflow de GitHub Actions encargado de eliminar el stack creado en AWS.

Este workflow permite destruir los recursos desplegados, incluyendo la instancia EC2 y el Security Group asociado.

---

### ec2.yaml

El archivo `ec2.yaml` contiene la plantilla de CloudFormation que define la infraestructura del proyecto.

La plantilla crea los siguientes recursos:

* Una instancia EC2.
* Un Security Group con acceso HTTP por el puerto 80.
* Un servidor Apache instalado automáticamente.
* Una página web generada mediante UserData.

---

## Funcionamiento del despliegue

El despliegue se realiza desde GitHub Actions ejecutando manualmente el workflow `Deploy EC2`.

Cuando se ejecuta este workflow, GitHub Actions se conecta a AWS utilizando las credenciales almacenadas como secretos del repositorio y despliega la plantilla `ec2.yaml`.

Una vez creada la instancia EC2, el UserData instala Apache y genera una página web pública accesible mediante la IP o DNS público de la instancia.

---

## Funcionamiento de la destrucción

La eliminación de los recursos se realiza ejecutando manualmente el workflow `Destroy EC2`.

Este workflow elimina el stack de CloudFormation llamado `examen-arqdepc-ec2-stack`, permitiendo borrar la instancia EC2 y los recursos asociados para evitar costos innecesarios en AWS.

---

## Git Flow utilizado

Para el desarrollo del proyecto se utilizó una estrategia basada en ramas independientes para cada actividad.

Las ramas utilizadas fueron:

* `feature/JDP_DeployEC2`
* `feature/JDP_DestroyEC2`
* `feature/JDP_TemplateEC2`
* `feature/JDP_ReadmeProject`

Cada rama contiene un commit específico y posteriormente fue integrada a la rama principal `main` mediante Pull Request.

---

## Commits principales

Los commits realizados en el proyecto fueron:

* Agregar workflow de despliegue EC2
* Agregar workflow de destruccion EC2
* Agregar template CloudFormation para EC2
* Agregar documentacion del proyecto

---

## Evidencias del proyecto

Como evidencia del desarrollo se deben presentar:

* Captura del repositorio en GitHub.
* Captura de las ramas creadas.
* Captura de los Pull Requests.
* Captura del workflow Deploy ejecutado correctamente.
* Captura del workflow Destroy ejecutado correctamente.
* Captura del stack creado en CloudFormation.
* Captura de la instancia EC2 creada.
* Captura de la página web funcionando en el navegador.

---

## Conclusión

Este proyecto permitió aplicar conceptos de infraestructura como código, automatización de despliegues y administración de recursos en la nube. Mediante el uso de AWS CloudFormation y GitHub Actions se logró crear, desplegar y eliminar una instancia EC2 de forma automatizada, cumpliendo con los requerimientos del examen final de Arquitectura de Computadores.