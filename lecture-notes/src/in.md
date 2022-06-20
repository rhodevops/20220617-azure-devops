---
title: "Azure Devops de cero a experto"
subtitle: "Por Alberto Picazo"
author: Roberto Negro
date: 17/06/2022
---

# Secciones anteriores

[TODO]

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

- Agentes hospedados por Microsoft
- Agentes autohospedados

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