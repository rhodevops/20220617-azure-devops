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

## Crear repositorio en Azure Repos

Dentro del proyecto, se navega a `Repos` y haciendo clic en `+`, existe una opción para crear un repositorio. 

También es posible importar un repo de un repositorio remoto (GitHub). Situados en en el tab `Repos`, en el panel superior se pude desplegar una ventana que contien la opción `Import repository`.

En el mismo desplegable existen una opción para gestionar los repositorios creados.

## Clonar repositorio en VSCode

Pasos:

- Crear un repositorio de git en AZ Devops
- Situado en el repositorio, seleccionar `Clone` (panel superior, derecha)
- Seleccioanar `Clone in VS Code` y seguir los pasos indicados
- Hay que elgir el directorio donde se situa el repo
- Es posible que se abra al `Git Crdential Manager`. En este caso hay que introducir las credenciales de nuestra cuenta de Microsoft.
- 




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

