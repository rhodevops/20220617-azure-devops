---
title: "Azure Devops de cero a experto"
subtitle: "Por Alberto Picazo"
author: Roberto Negro
date: 17/06/2022
---

# Introducción

## Definiciones y algunas instalaciones

- VSCode
- Concepto de Devops

## ¿Qué es Azure Devops?

AZ Devops es una plataforma que centraliza todo lo que necesita el ciclo de vida de una aplicación. Varios módulos:

- Azure Repos $\to$ CVS (Git)
- Azure Pipelines $\to$ CI y CD, despliegues automáticos
- Azure Boards $\to$ gestión del proyecto
- Azure Test Plans $\to$ herramientas de pruebas
- Azure Artifacts $\to$ gestor de paquetes

# Configuración de la organización en AZ Devops

Se navega a `Organization Settings` (abajo, izquierda)

## Configuraciones generales

General tab:

- `Overview` generales
- `Projects` proyectos
- `Users` usuarios de organización/proyecto
- `Billing` facturación (extensiones de pago)
- `Auditing` trazas de las acciones de auditoria realizadas
- `Global Notifications` gestionar notificaciones globales
- `Usage` usos/límites
- `Extensions` extensiones
- `AZ AD` Azure Active Directory (usuarios/roles)
- `Usage`

## Configuración de la Seguridad

Security tab:

- `Policies` (OAuth, SSH)
- `Permissions` (de grupo, de usuario): distintos roles

## Configuración de procesos

Boards tab:

- `Process` Procesos de gestión de proyectos

Tipos: Basic, Agile, Scrum, CMMI

## Configuración de pipelines

Pipelines tab:

- `Agent Pools` MS-hosted o self-hosted (lm, AZ vm)
- `Settings` des(habilitar) límites
- `Deployment pools` grupos de despliegues a sitios concretos
- `Parallel jobs` hacer builds/jobs/acciones en paralelo (no hay cola de jobs)
- `OAuth configurations` configurar accesos OAuth

## Configuración de repos

Repos tab:

- `Repositories` configuraciones

## Configuración de artifacts

Artifacts tab:

- `Storage` Capacidad de almacenaje disponible

# Configuración de un proyecto en Azure Devops

Dentro del proyecto, se navega a `Organization Settings` (abajo, izquierda)

## Proyecto en AZ Devops

Los proyectos dentro de una empresa/departamento.

## Configuracion general del proyecto

General tab:

- `Overview`
- `Teams`
- `Permissions`
- `Notifications` pull request, etc
- `Service hooks` conectores, reaccionar a eventos
- `Dashboards`

## Configuracion boards del proyecto

Boards tab:

- `Project configuration` configurar sprints
- `Team configuration` 
- `GitHub connections` traer información del GitHub

## Configuracion de las pipelines del proyecto

Pipelines tab:

- `Agent Pools` MS-hosted o self-hosted (lm, AZ vm)
- `Parallel jobs` hacer builds/jobs/acciones en paralelo (no hay cola de jobs)
- `Settings` des(habilitar) límites
- `Test Management` configurar Flaky test (pruebas)
- `Release retention` días de retención de la release
- `Service connections` conectar cuentas de AZ, GitHub, etc (integración)
- `XAML build services` crear nuevos servicios de AZ de forma manual


## Configuracion de los repos del proyecto

Repos tab:

- `Repositories` repositories, settings, policies, security

## Configuracion de los artifacts del proyecto

Artifacts tab:

- `Storage`

## Configuracion de los tests del proyecto

Test tab:

- `Retention` días que se mantienen los resultados de los test

# Metodología Agile

## ¿Qúe se hacía antes? Waterfall

La metodología en cascada o Waterfall:

- Dividido en distintas fases (p.e. construcción de un coche)
- Rígido
- Enfoque secuencial (cada fase una sola vez)
- Requisitos la inicio del proyecto
- Completar el proyecto

## ¿Qué se hace ahora? Agile

- Ciclo de vida en sprints
- Flexible
- Enfoque iterativo (vuelta a la misma fase)
- Los requisitos cambian y evolucionan
- Cumplir las exigencias del cliente

Buscar más información.

# Módulo Overview

## Summary

Resumen del proyecto.

## Dashboards

- Paneles que se pueden configurar.
- Hay distintos widgets que se pueden agregar.
- Hay una Extensión Gallery (un marketplace)

## Wiki

Escribir la documentación general del proyecto.

- `Create project wiki`
- `Publish code as wiki` copiar de los README.md de los propios repositorios

# Módulo Boards

[TODO]

# Modulo Repos

## ¿Qué es Azure Repos?

Conjunto de herramientas de control de versiones para adminsitar el código. Se pude utilizar:

- `Git` (sistema distribuído)
- `TFVC` (sistema centralizado) Team Foundation VC

## Crear un AZ Repos Git

Dentro del proyecto, se navega a `Repos` y haciendo clic en `+`, existe una opción para crear un repositorio. 

También es posible importar un repositorio remoto (de GitHub). Situados en el tab `Repos`, en el panel superior se pude desplegar una ventana que contiene la opción `Import repository`.

En el mismo desplegable existen una opción para gestionar los repositorios creados.

## Subir código a AZ Repos Git

Vamos a partir de un AZ Repos Git vacío (o con el README). Lo vamos a sincronizar con un directorio local y luevo vamos a subir al repositorio de AZ DEvops código creado en local.

- Crear un nuevo `AZ Repos Git`.

Dos formas para hacer la sincronización.

1. Utilizando la opción `Clone in VS Code`

    - Situados en el AZ Repos, seleccionar `Clone` (panel superior, derecha).
    - Seleccioanar `Clone in VS Code` y seguir los pasos indicados.
    - Hay que elegir el directorio local donde se situa el repo.
    - Es posible que se abra una venta de `Git Credential Manager`. En este caso hay que introducir las credenciales de nuestra cuenta de Microsoft.

2. Haciendo un `git clon` por línea de comandos:

    - Situados en el AZ Repos, seleccionar `Clone` y copiamos la url del repositorio.
    - Desde el directorio donde queremos incluir el repo, hacemos un `git clon <url>`

En este punto (tras 1 o tras 2) los repositorios local y remoto ya están sincronizados. Si hacemos un `git remote -v` en el directorio local creado, se muestra la url del repositorio de AZ Devops:

```bash
$ git remote -v
origin  https://rhodevops@dev.azure.com/rhodevops/20220617-azure-devops/_git/test (fetch)
origin  https://rhodevops@dev.azure.com/rhodevops/20220617-azure-devops/_git/test (push)
```

Pasos para subir código (modo habitual):

- Añadir/modificar archivos al repositorio local.
- Subir archivos al stage y hacer commit.
- `git remote -v` para verificar la url de subida
- Hacer el push

## Subir código a AZ Repos Git II

Repositorio del laboratorio: `lab07001`

Vamos a partir de un AZ Repos Git vacío (o con el README).

Pasos para hacer la sincronización:

- Crear un nuevo `AZ Repos Git`.
- Situados en el repositorio, seleccionar `Clone` (panel superior, derecha).
- Seleccioanar `Clone in VS Code` y seguir los pasos indicados.
- Hay que elegir el directorio local donde se situa el repo.
- Es posible que se abra una venta de `Git Credential Manager`. En este caso hay que introducir las credenciales de nuestra cuenta de Microsoft.
- En este punto ya está sincronizado. Si hacemos un `git remote -v` se muestra la url del repositorio de AZ Devops.

Pasos para subir código (modo habitual):

- Añadir/modificar archivos al repositorio local.
- Subir archivos al stage y hacer commit.
- `git remote -v` para verificar la url de subida
- Hacer el push

## Crear ramas en el repositorio

Repositorio del laboratorio: `lab07001`

Dentro del proyecto de AZ Devops, se navega a `Repos - Branches` y se selecciona `New Branch`. Hay que indicar la rama antigua en la que se basa la nueva rama.

En nuestro caso, consideraremos que la rama `main` es la de PRO. Vamos a crear la rama `PRE` basada en la de producción y la rama `DEV` basada en la rama de preproducción.

Además utilizamos el desplegable de tres puntos de la rama `DEV` para establecer la rama de desarrollo como `default` and `compare`.

## Política de ramas

Repositorio del laboratorio: `lab07001`

Las branch policies sirven para proteger las ramas ante prácticas indeseadas.

Para configurar una política en una rama, navegamos a `Repos - Branches` del repo deseado y, en la rama objetivo, desplegamos las opciones de tres puntos y seleccionamos `Branch Policies`    

Configuramos la rama `DEV` como se muestra en la figura `DEV Branch Policies`:

- Se requiere aprobación por una persona
- Se permite autoaprobar
- Se requiere comentario

![DEV Branch Policies](./images/DEV-branch-policies.PNG)

Con estas políticas, cuando intentamos modificar un archivo de la rama `DEV` y hacer un commit del cambio, nos salta un error. El error nos indica que no está permitido hacer un push a la rama y que necesitamos usar una pull request para actualizar la rama.

![Testing DEV Branch Policies](./lecture-notes/images/testing-DEV-branch-policies.PNG)

En la siguiente sección se trata este caso.

## Solicitud de cambios. Pull Request

Repositorio del laboratorio: `lab07001`

Conceptos previos:

- Una `Pull Request` (`Merge Request` en GitLab) es una solicitud, p.e. de un desarrollador, para que el código que ha creado en su rama se integre en otra.
- Normalmente la rama del desarrollador es de tipo `feature` y muere tras integrarse en una rama de mayor nivel como puede ser `DEV`.
- La `Pull Request` normalmente es resuelta por una persona distinta a la persona que ha hecho la solicitud.

El desarrollador crear una Pull Request:

- Crear una rama de tipo feature basada en la rama `DEV`. 
- Si la llamamos `feature/prueba-dev`, se crea una rama llamada `prueba-dev` dentro de la carpeta `feature`.

![Feature branch based on DEV branch.](./lecture-notes/images/feature-branch-based-on-DEV-branch.PNG)

- Modificar un archivo del repo en la rama de tipo feature y crear una `Pull Request`. 
- La `Pull Request` se pude crear en `Repos - Files` o en `Repos - Pull Request`. 
- En ambos casos hay que seleccionar la rama y el repo correspondiente.
- Y en el segundo caso hay que explicitar en que rama (`DEV`) se integra la rama feature.
- Completar los campos indicados en la solicitud. 
- Debido a las policies establecidas en la rama `DEV` hay que que añadir un viewer.

El devops gestiona la Pull Request y hace el `Approve`:

- Si se aprecia algún fallo de código, el devops puede poner un comentario al desarrollador.
- Debido a las políticas de la rama `DEV`, no se puede hacer el `Complete` hasta que no se resuelva el comentario, como se muesta en la figura `Pull Request. Comments must be resolved` (Si que se puede hacer un `Aprove` aunque no tiene mucho sentido). 

![Pull Request. Comments must be resolved](./lecture-notes/images/Pull-Request-Comments-must-be-resolved.PNG)

- El desarrollador resuelvo el fallo detectado, hace el commit correspondinte y acude a la `Pull Request` para hacer un `Reply and Resolve` en el comentario que le ha puesto el devops. El devops se encarga de ir poniendo en `Closed` o `Resolved` el estado de los distintos comentarios.

![Pull Request. Reply and resolve](./lecture-notes/images/Pull-Request-Reply-and-resolve.PNG)

- Resueltos los comentarios, el devops hace el `Approve` e inicia el `Conmplete`

![Pull Request. Approve](./lecture-notes/images/Pull-Request-Approve.PNG)

- Hay varios tipos de `Complete`, en este caso se hace un `Merge (no fast forward)`. Hay varias opciones a completar, entre ellas la eliminación de la rama que se ha integrado (habitual en la integración de ramas feature)

![Pull Request. Complete merge](./lecture-notes/images/Pull-Request-Complete-merge.PNG)

## Tags





# Módulo pipelines CI

## Activar modo gratuido de Azure Pipelines

Consultar video del curso.

## ¿Qué es Azure Pipelines?

Azure Pipelines es uno de los módulos más importantes.

- Combina CI y CD.
- Compilar y prueba automáticamente los proyecos de código
- Poner el proyecto a disposición de otros usuarios.

## Importar un repositorio desde GitHub

En `Repos` se utiliza la opción `Import Repository` y se hace un clon de un repositorio de Github.

## Agentes

Un agente es una máquina/contenedor/programa que actúa para un usuario u otro programa:

- No es invocado estrictamente por una tarea, sino que se activa el mismo.
- Puede estar en un servidor en estado de espera.
- No requiere acción de los usuarios.
- Puede invocar otras tareas incluyendo comunicación.

Tipos de agentes:

- Microsoft-hosted agents
- Self hosted agents (local machine, azure machine, etc)

Consultar [docs.microsoft.com/es-es/azure/devops/pipelines](https://docs.microsoft.com/es-es/azure/devops/pipelines/agents/hosted?view=azure-devops&tabs=yaml) para ver lo que contiene cada uno de los Microsoft-hosted agents. 

Si se utilizan agentes autohospedadado, el mantenimiento corre de tu parte.

## Lab: crear un agente self-hosted usando una azure vm

Este laboratorio también se puede hace usando una máquina local en lugar de la Azure vm.

### Desplegar una vm en Azure

Pasos:

- Crear un máquina virtual.
- Conectar por RDP file.

### Configurar la vm

Accedemos a la vm. Configuramos la vm para que pueda compilar/operar nuestros programas.

- Instalar algunas herramientas de la Visual Studio Build Tools
- Instalar powershell 7
- Instalar .NET SDK

### Crear un token en Azure Devops

En Azure Devops, en el panel superior (derecha), buscamos la opción `Personal Access tokens` y generamos un token con los permisos deseados.

### Configurar el agente en Devops

Dentro del proyecto de Azure Devops, en `Project Settings` se navega a `Pipelines - Agent Pools`. Dentro del pool `Default`, creamos un nuevo agente (`New agent`).

Seguimos las intruciones indicadas:

- Descargar el zip del agent y descomprimir
- Renombramos la carpeta a `agent`
- Abrir una Poweshell y seguir los pasos indicados en Azure Devops.
- Hay que ejecutar el archivo de configuración y luego el archivo de ejecutar.

Tras estos pasos, aparece el agente configurado dentro del pool.

## Configuración de agentes

Dentro del proyecto de Azure Devops, en `Project Settings` se navega a `Pipelines - Agent Pools`. 

- Los pool `Default` y `Azure Pipelines` vienen ya creados.
- El pool `Azure Pipelines` contiene los agentes proporcionados por Microsoft. 
- El pool `Default` contiene los agentes creados por nosotros.

## Crear una pipeline utilizando una plantilla

En AZ Devops, se navega Pipelines/Pipelines y se hace clic en `Create Pipelin`. En este caso, se indica que el código está en un `Azure Repos Git` (hay que importarlo a AZ Devops). 

Podemos utilizar una plantilla predefinida, en este caso utilizamos la de `ASP.NET Core` por el tipo de código que tenemos en el repositorio. Finalmente, ordenamos `Save and Run`.

Podemos consultar las ejecuciones de los `Jobs`

## Crear una pipeline utilizando la vista clásica

En AZ Devops, se navega Pipelines/Pipelines y se hace clic n `Create Pipelin`. 
En el primer paso, se accede a la opción `Use the classic editor`.

La opción clásica tiene varias desventajas y no es la forma standard que se utiliza en el año 2022.

## Crear distintivos (badgers) de estado

En AZ Devops, navegamos a Pipeline/Pipeline, seleccionamos una pipeline y hacemos clic en el icono de 3 puntos situado junto al `Run pipeline` (parte superior derecha). Seleccionamos `Status Badge` y podemos copiar tanto la `image url` como el `sample markdown`.

Los distintivos se puden incrustar en varios sitios: en una Wiki, en un Dashboard, en el Readme del respositorio asociada a la pipeline, etc

