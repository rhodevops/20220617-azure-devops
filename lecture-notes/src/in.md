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

## ¿Qué es AZ Boards?

Con `AZ Boards` proporciona un sistema de gestion de los proyectos. 

Características_

- Soporte nativo para Scrum y Kanban.
- Tipos de procesos: `agile`, `basic`, `scrum`, `CMMI`.
- Permite colaboración dentro del equipo.
- Trabajo en Sprints

## Gestión de usuarios

### Invitar a usuarios

En `Organization Settings`, en la pestaña `Users`, existe la opción `Add Users` para añadir nuevos usuarios a los proyectos de la la organización.

También se puede utilizar la opción `Invite`, en la pestaña `Overview - Summary`, para añadir usuarios.

### Seguridad de usuarios

En `Organization Settings`, en la pestaña `Users`, se puede utilizar la opción `Manage user`del desplegable de tres puntos de un usuario para gestionar sus permisos y niveles de acceso.

## Tipos de procesos

- `agile` metodologías ágiles
- `basic` modelo más simple
- `scrum` metodología scrum
- `CMMI` métodos de proyecto más formales (marc mejora procesos, registro auditable de decisiones) 

## Pendiente

[PENDIENTE](todo)

Falta por incluir los apuntes relativos a:

- Kanban en Azure Boards
- Configurar capacidad del equipo
- Configurar columnas en los paneles
- Configuración de paneles
- Filtrando tareas con Querys
- Configura tus equipos
- Configura Dashboards para ver metricas sobre Azure Boards
- Practica

Si es necesario, consultar los videos correspondientes. La práctica parece interesante.

# Modulo Repos

## ¿Qué es Azure Repos?

Conjunto de herramientas de control de versiones para adminsitar el código. Se pude utilizar:

- `Git` (sistema distribuído)
- `TFVC` (sistema centralizado) Team Foundation VC

## Crear un AZ Repos Git

Dentro del proyecto, se navega a `Repos` y haciendo clic en `+`, existe una opción para crear un repositorio. 

También es posible importar un repositorio remoto (de GitHub). Situados en la pestaña `Repos`, en el panel superior se pude desplegar una ventana que contiene la opción `Import repository`.

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

Repositorio del laboratorio: `lab0701`

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

Repositorio del laboratorio: `lab0701`

Dentro del proyecto de AZ Devops, se navega a `Repos - Branches` y se selecciona `New Branch`. Hay que indicar la rama antigua en la que se basa la nueva rama.

En nuestro caso, consideraremos que la rama `main` es la de PRO. Vamos a crear la rama `PRE` basada en la de producción y la rama `DEV` basada en la rama de preproducción.

Además utilizamos el desplegable de tres puntos de la rama `DEV` para establecer la rama de desarrollo como `default` y `compare`. Está última opción sirve para fijar una referencia cuando en en `Repos - Branches`, se utiliza la opción de tres puntios `Compare branches`.

## Política de ramas

Repositorio del laboratorio: `lab0701` 

Las branch policies sirven para proteger las ramas ante prácticas indeseadas.

Para configurar una política en una rama, navegamos a `Repos - Branches` del repo deseado y, en la rama objetivo, desplegamos las opciones de tres puntos y seleccionamos `Branch Policies` 

![DEV Branch Policies](./images/DEV-branch-policies.PNG)

Observar la nota bajo el título de la ventana emergente:

> If any required policy is enabled, this branch cannot be deleted and **changes must be made via pull request**.

Configuramos la rama `DEV` como se muestra en la Figura ['DEV Branch Policies'](fig):

- Se requiere aprobación por una persona
- Se permite autoaprobar
- Se requiere comentario

Al establecer políticas, cuando intentemos modificar un archivo de la rama `DEV` y hacer un commit del cambio, nos saltara un error. El error nos indicará que que los cambios deben hacerser vía pull requests.

![Testing DEV Branch Policies](./images/testing-DEV-branch-policies.PNG)

En la siguiente sección se trata este caso.

## Solicitud de cambios. Pull Request

Repositorio del laboratorio: `lab0701` 

Conceptos previos:

- Una `Pull Request` (`Merge Request` en GitLab) es una solicitud, p.e. de un desarrollador, para que el código que ha creado en su rama se integre en otra.
- Normalmente la rama del desarrollador es de tipo `feature` y muere tras integrarse en una rama de mayor nivel como puede ser `DEV`.
- La `Pull Request` normalmente es resuelta por una persona distinta a la persona que ha hecho la solicitud.

El desarrollador crear una Pull Request:

- Crear una rama de tipo feature basada en la rama `DEV`. 
- Si la llamamos `feature/prueba-dev`, se crea una rama llamada `prueba-dev` dentro de la carpeta `feature`.

![Feature branch based on DEV branch](./images/feature-branch-based-on-DEV-branch.PNG)

- Modificar un archivo del repo en la rama de tipo feature y crear una `Pull Request`. 
- La `Pull Request` se pude crear en `Repos - Files` o en `Repos - Pull Request`. 
- En ambos casos hay que seleccionar la rama y el repo correspondiente.
- Y en el segundo caso hay que explicitar en que rama (`DEV`) se integra la rama feature.
- Completar los campos indicados en la solicitud. 
- Debido a las policies establecidas en la rama `DEV` hay que que añadir un viewer.

El devops gestiona la Pull Request y hace el `Approve`:

- Si se aprecia algún fallo de código, el devops puede poner un comentario al desarrollador.
- Debido a las políticas de la rama `DEV`, no se puede hacer el `Complete` hasta que no se resuelva el comentario, como se muesta en la Figura ['Pull Request. Comments must be resolved'](fig) (Si que se puede hacer un `Aprove` aunque no tiene mucho sentido). 

![Pull Request. Comments must be resolved](./images/Pull-Request-Comments-must-be-resolved.PNG)

- El desarrollador resuelvo el fallo detectado, hace el commit correspondinte y acude a la `Pull Request` para hacer un `Reply and Resolve` en el comentario que le ha puesto el devops. El devops se encarga de ir poniendo en `Closed` o `Resolved` el estado de los distintos comentarios.

![Pull Request. Reply and resolve](./images/Pull-Request-Reply-and-resolve.PNG)

- Resueltos los comentarios, el devops hace el `Approve` e inicia el `Conmplete`

![Pull Request. Approve](./images/Pull-Request-Approve.PNG)

- Hay varios tipos de `Complete`, en este caso se hace un `Merge (no fast forward)`. Hay varias opciones a completar, entre ellas la eliminación de la rama que se ha integrado (habitual en la integración de ramas feature)

![Pull Request. Complete merge](./images/Pull-Request-Complete-merge.PNG)

## Tags

Repositorio del laboratorio: `lab0701`

Los tags sirven para etiquetar los distintos estados de un repositorio (commits) a lo largo de su vida. 

- Pueden estar basados en commits, branches u otros tags.
- Se puden tener varios tags en el mismo commit.
- Pueden identificar versiones p.e. `2.3.1`
- Pueden identificar otros aspectos p.e. `entrega-uat`

Los tags se gestionan desde la pestaña `Repos - Tags`. Sin embargo, es más cómodo agregar un tag basado en un commit desde la pestaña `Repos - Commits`, utilizando las opciones de tres puntos.

![Tags based on commits](./images/Tags-based-on-commits.PNG)


Desde `Repos - Tags`, se puede establecer el `compare` tag para establecerlo como referencia al utilizar la opción `Compare tags`.

Algunos usos de los tags:

- En `Repos - Files`, visualizar estados concretos del repo buscando por tags.
- En `Repos - Tags`, utilizar la opción `Compare tags` y comparar por tags.

## Concepto de fork

Es importante distinguir los términos `clone` (proceso) y `fork` (concepto). 

Es bastante esclarecedor pensar en `clone` como un comando de git que crea una copia de un repositorio y pensar en `fork` como la práctica que permite, bien hacer una bifurcación independiente de un proyecto, o bien iniciar una colaboración en un proyecto (si tengo permisos) realizando propuestas a través de pull requests.

Las figuras ['Clon repository'](fig) y ['Fork repository'](fig) muestran de manera gráfica la situación. 

![Clone repository](./images/Clone-repository.PNG)

![Fork repository](./images/Fork-repository.PNG)

Es importante tener claro que:

- El `clon` se hace usando git, mientras que el `fork` se hace en la cuenta de GitHub.
- El `clone` crea un copia en tu máquina local, mientras que el el `fork` crea una copia en tu cuenta de GitHub.

Conceptos:

- `Original Repo` El repositorio original.
- `Forked Repo` El repositorio donde se encuentra la copia del original.

Flujo de trabajo tras hacer un `fork`. Se distinguen dos casos:

- Tengo permisos de escritura sobre el repo original
    1. Tras hacer el `fork` en GitHub, se hace un `clon` a la máquina local.
    2. Los cambios locales se `pushean` al repo forkeado.
    3. Se envia una `pull request` al repo original para proponer cambios. 

- No dispongo de permisos de escritura sobre el repo original
    1. Idem anterior.
    2. Idem anterior.
    3. No puedo colaborar en el proyecto original.
  
## Forks en AZ Devops

Repositorio del laboratorio: `lab0701` 

Se puden hacer por varios motivos:

- Hacer pruebas sin afectar al repositorio original
- Bifucar el repositorio par plantear otra solución
- Etc

Para crear un Fork:

Se navega al repo en `Repos - Files` y en la opción de tres puntos (junto a `Clone`) se seleciona la opción `Fork`. En este caso, lo llamamos `Fork de lab0701` y aparecerá junto al resto de repos pero con el icono de repo en blanco y negro (en lugar del naranja habitual).

Para hacer un `Pull Request` desde el Fork al Original:

Situado en el repo del Fork, navegamos a la pestaña `Repos - Pull requests` y hacemos la peticion. En la imagen se muesta un ejemplo:

![Forks. Pull request](./images/Forks-Pull-request.png)

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

Repositorio del laboratorio: `lab0801` (local)

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

## Crear una pipeline con código en GitHub

Repositorio del laboratorio: `FORK-python-sample-vscode-flask-tutorial` (fork en GitHub)

Pipeline con código en GiHub:

- Se siguen las indicaciones de [Create your first pipeline](https://docs.microsoft.com/en-us/azure/devops/pipelines/create-first-pipeline?view=azure-devops&tabs=python%2Ctfs-2018-2%2Cbrowser)
- Se utiliza un fork de GitHub.
- El archivo YAML de la pipeline se almacena en el repo de GitHub.
- Si el YAML de la pipeline ya existe en GitHub, se puede seleccionar con la opción `Existing Azure Pipelines YAML file`.
- Y en el caso de que se llame `azure-pipelines.yml` se detecta automáticamente.

En GitHub hacemos un fork del proyecto [https://github.com/microsoft/python-sample-vscode-flask-tutorial](https://github.com/microsoft/python-sample-vscode-flask-tutorial) y lo nombramos `lab0802-python-sample-vscode-flask-tutorial`.

En AZ Devops, se navega Pipelines/Pipelines y se hace clic en `Create Pipeline`. En este caso, se indica que el código está en `GitHub`.

Uilizamos la plantilla `Python package`, por el tipo de código que tenemos en el repositorio. Finalmente, ordenamos `Save and Run`.

Podemos consultar las ejecuciones de los `Jobs`.

Editamos la pipeline para eliminar el job `Job Python35`.

El código final es el siguiente:

```yaml
# Python package
# Create and test a Python package on multiple Python versions.
# Add steps that analyze code, save the dist with the build record, publish to a PyPI-compatible index, and more:
# https://docs.microsoft.com/azure/devops/pipelines/languages/python

trigger:
- master

pool:
  vmImage: ubuntu-latest
strategy:
  matrix:
    Python27:
      python.version: '2.7'
    Python36:
      python.version: '3.6'
    Python37:
      python.version: '3.7'

steps:
- task: UsePythonVersion@0
  inputs:
    versionSpec: '$(python.version)'
  displayName: 'Use Python $(python.version)'

- script: |
    python -m pip install --upgrade pip
    pip install -r requirements.txt
  displayName: 'Install dependencies'

- script: |
    pip install pytest pytest-azurepipelines
    pytest
  displayName: 'pytest'
```

Notas importantes:

- Por defecto, la rama por defecto de la pipeline es la `default branch` del repo.
- Las pipelines creadas desde la pestaña `Pipelines` se crean en la `default branch`, salvo que en ventana correspodiente se cambie la opción a otra rama.
- También se puede crear una pipeline desde la pestaña `Repos - Files`. La opción se llama `Set up build`.

## Crear una pipeline con código en Azure Devops

Repositorio del laboratorio: `lab0802-pipelines-dotnet-core`

Pipeline con código en Azure Repos Git:

- Se utiliza un repo de Azure Devops.
- El archivo YAML de la pipeline se almacena en el repo de Azure Devops.

Se crea un repo en AZ Devops importándolo (clon) de GitHub. El projecto es [https://github.com/MicrosoftDocs/pipelines-dotnet-core](https://github.com/MicrosoftDocs/pipelines-dotnet-corel). Se pone de nombre `lab0803-pipelines-dotnet-core`.

En AZ Devops, se navega a `Pipelines/Pipelines` y se hace clic en `Create Pipeline`. En este caso, se indica que el código está en un `Azure Repos Git`. 

Podemos utilizar una plantilla predefinida, en este caso utilizamos la de `ASP.NET Core` por el tipo de código que tenemos en el repositorio. Finalmente, ordenamos `Save and Run`.

Podemos consultar las ejecuciones de los `Jobs`.

Se edita la pipeline con lo siguiente:

- Un `steps.task` que contiene dos `echo` de terminal bash
- Para introducir lo anterior se utiliza el panel de ayuda `Tasks`
- Parámetros `environment` y `region` para seleccionar antes de ejecutar la pipeline.

El código final es el siguiente:

```yaml
# ASP.NET Core
# Build and test ASP.NET Core projects targeting .NET Core.
# Add steps that run tests, create a NuGet package, deploy, and more:
# https://docs.microsoft.com/azure/devops/pipelines/languages/dotnet-core

trigger:
- master

pool:
  vmImage: ubuntu-latest

parameters:
  - name: environment
    type: string
    displayName: Environment
    values:
      - PRE
      - PRO
  - name: region
    type: string
    displayName: Region
    values:
      - EU
      - US

variables:
  buildConfiguration: 'Release'

steps:
- script: dotnet build --configuration $(buildConfiguration)
  displayName: 'dotnet build $(buildConfiguration)'
- task: CmdLine@2
  inputs:
    script: |
      echo Entorno de ejecución: ${{parameters.environment}}
      
      echo Región: ${{parameters.region}}
```

Nota:

- Las pipelines se pueden ordenar en carpeta en Azure Devops. Se gestiona desde la pestaña `Pipelines - pipelines`

## Crear una pipeline utilizando la vista clásica

En AZ Devops, se navega Pipelines/Pipelines y se hace clic en `Create Pipeline`. 
En el primer paso, se accede a la opción `Use the classic editor`.

Uso de la vista clásica para generar YAML:

- Crear una pipeline clasica.
- Editarla y situarse en el `Agente Job` como se muesta en la Figura ['Pipeline classic editor. View yaml'](fig).
- En la misma figura, se observa la opción `View YAML` que se puede utilizar.
- Crear una nueva pipeline con el código YAML generado.
- ¡Cuidado! Podemos tener problemas con las variables de entorno o conexiones a servidores.
- Revisar el código una vez generado.

![Pipeline classic editor. View yaml](./images/Pipeline-classic-editor-View-yaml.png)

Otra opción, es exportar pipeline clásica a YAML:

- En la pestaña `Pipelines - Pipelines`, se accede a la classic pipeline que nos interese.
- Dentro, junto a la opción `Run pipeline`, se utiliza el desplegable de tres puntos.
- Se utilizar la opción `Export to YAML` para generar el archivo YAML.

## Crear distintivos (badgers) de estado

En AZ Devops, navegamos a Pipeline/Pipeline, seleccionamos una pipeline y hacemos clic en el icono de 3 puntos situado junto al `Run pipeline` (parte superior derecha). Seleccionamos `Status Badge` y podemos copiar tanto la `image url` como el `sample markdown`.

Los distintivos se puden incrustar en varios sitios: en una Wiki, en un Dashboard, en el Readme del respositorio asociada a la pipeline, etc

## Configurar la ejecución de una pipeline en una Pull Request

Repositorio del laboratorio: `lab0701`

### Parte 1. Ejecutar una pipeline en una rama protegida por policies 

Notas iniciales:

- `DEV` es la default branch 
- `DEV` está protegida por policies (**changes must be made via pull request**.)

En la pestaña `Pipelines - pipelines`, se crear una pipeline de la forma habitual, pero como no se puede hacer un commit directo a la rama `DEV`, es necesario crear una rama para hacer el commit, se llamará `azure-pipelines-add`.

![New pipeline with pull request](./images/New-pipeline-with-pull-request.PNG)


### Parte 2. Configurar una pipeline de CI

El objetivo es configurar una pipeline que se ejecutará cada vez que haya una pull request hacia la rama DEV.

En la pestaña, `Files - Branches`, se configura una policie sobre la rama `DEV` de tipo `Build validation`.

![DEV policies. Build validation](./images/DEV-policies-Build-validation.PNG)

Se dejan las opciones por defecto. Observar la opción `Triger.Automatic` que dispara la pipeline cada vez que la `source branch` se actualiza (CI).

![CI pipeline. Configuration of buid validation](./images/CI-pipeline-Configuration-of-buid-validation.PNG)

### Parte 3. Probar la pipeline de CI

Para probar la pipeline de CI:

- Se crea una nueva rama `feature/pipeline-test`
- Se hace un cambio/commit sobre la rama creada
- Se abre una pull request a la rama DEV

![New branch feature: pipeline-test](./images/New-branch-Feature-pipeline-test.PNG)
)

En la Figura ['Test a CI pipeline'](fig), se observan los requerimientos que deben cumplirse para que se complete la pull request.

![Test a CI pipeline](./images/Test-a-CI-pipeline.PNG)

## Configurar la ejecución de una pipeline tras un cambio en una rama

Repositorio del laboratorio: `lab0802-pipelines-dotnet-core` 

La propiedad `pipeline.trigger` especifica que rama causa la ejecución de un trabajo de CI. En el caso del código mostrado, un cambio en la rama `master` hace que se dispare la pipeline:

```yaml
trigger:
- master

pool:
  vmImage: ubuntu-latest

[...]
```

**Nota importantes** Cuando una pipeline que requiere paso de parámetros (intervención manual) se dispara automáticamente, debido a un commit, la ejecución da error. Precisamente porque no se ha pasado el parámetro. Investigar una posible solución.

## Crear el código YAML de una pipeline

Repositorio del laboratorio: `lab0803-pipelines`

### Conceptos previos fundamentales

#### Pipelines

- Una `pipeline` es un conjunto de tareas ejecutadas en un flujo de trabajo.
- Azure Devops ofrece dos tipos de pipelines.
- La `Build Pipeline` se usa para generar `artifacts` fuera del código fuente.
- La `Release Pipeline` consume los `artifacts` y lleva a cabo accciones de seguimientos dentro de un sistema `multi-staging`. 
- Es una buena práctica establecer un enlace entre una  `Build Pipeline` y su correspondiente `Release Pipeline`.

#### Jobs, agents y pools

- Un `job` es una unidad de trabajo asignada a un agente o un servidor.
- Un `agent` es un programa/contenedor/vm que ejecuta los trabajos de la pipeline.
- Un `agent pool` (grupo de agentes) ayuda a organizar y gestionar los agentes instalados en diferentes entornos. Se pueden usar en pipelines de tipo `Release` y `Build`.
- Un `deployment pool` es otro grupo de agentes. Solo se pueden usar en pipelines de tipo `Release`. Lo forman las máquinas objetivo del despliegue. Representa el entorno (DEV, TEST, UAT, PRO). 

#### Stages, jobs, steps, tasks

Constituyen la estructura de una pipeline "completa". 

- Un `stage` es un escenario o etapa de ejecución. 
- Un `job` es un trabajo dentro de un stage.
- Los `steps` son secuencias lineales de operaciones dentro de un job. Varios tipos:
  - `steps.task` es un bloque de código de una pipeline. 
  - `steps.script`
  - `steps.bash`
  - etc

Hay que aclarar que una pipeline simple no requiere de todos estos niveles. 

Jerarquicamente:

```yaml
Pipeline
  Stage A
    Job 1
      Step 1.1
      Step 1.2
      ...
    Job 2
      Step 2.1
      Step 2.2
      ...
  Stage B
  ...
```

Y con la sintaxis utilizada en el YAML:

```yaml
stages:
  - stage: StageA
    jobs:
      - job: job1
        steps:
          - [ step ]
          - [ step ]
            [ ... ]
      - job: job2
        steps:
          - [ step ]
          - [ step ]
            [ ... ]
  - stage: StageB
    [ ... ]
```

### Pipeline 01: trigger, variables y jobs

Conceptos:

- Un `trigger` es un disparador de la pipeline.

Código:

```yaml
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml

name: $(Date:yyyyMMdd)$(Rev:.r)_$(SourceBranchName)

trigger:
  branches:
    include:
      - master
    exclude:
      - DEV

pool:
  vmImage: ubuntu-latest

variables:
  name: Roberto

jobs:
  - job: trabajo1
    steps:
      - script: echo Hello, $(name)
        displayName: Say Hello

  - job: trabajo2
    steps:
      - script: echo Bye, $(name)
        displayName: Say Bye
```

Notas del código:

- `$(name)` es una variable definida en `variables.name`
- La propiedad `pipelines.name` define el número de ejecución de la pipeline
- La variable `$(Rev:.r)` sirve como contador del número de ejecuciones de la pipeline.
- El valor por defecto de `pipelines.name` es `pipelines.name = $(Date:yyyyMMdd)$(Rev:.r)`

### Pipeline 02: parameters

Código:

```yaml
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml

name: $(Date:yyyyMMdd)$(Rev:.r)_$(SourceBranchName)

pool:
  vmImage: $(vmImage)

parameters:
  - name: vmImage
    values:
      - Ubuntu 18.04
      - Ubuntu 20.04

variables:
  - ${{ if eq(parameters.vmImage, 'Ubuntu 18.04') }}: 
    - name: vmImage
      value: ubuntu-18.04
  - ${{ if eq(parameters.vmImage, 'Ubuntu 20.04') }}: 
    - name: vmImage
      value: ubuntu-20.04


jobs:
  - job: myjob
    displayName: My first job
    dependsOn: A
    workspace:
      clean: outputs
    steps:
      - script: echo Mi primer trabajo
  - job: A
    steps:
      - script: echo Este es el trabajo A
```

Notas del código:

- El agente del pool esta parametrizado (`parameters.vmImage`)
- El valor de la variable `$(vmImage)` está condicionado al valor del parámetro `parameters.vmImage` que se le pasa a la pipeline.
- La propiedad `jobs.job.dependsOn` se utiliza para indicar que un trabajo depende de otro. En la práctica se traduce en que uno se ejecuta antes que otro.

### Pipeline 03: stages y steps

Jerárquicamente, tenemos `stages`, `jobs`, `steps`.

- Los `pipelines.stages` y los `jobs.job.steps` se ejecutan secuencialmente.

Código:

```yaml
# Starter pipeline
# Start with a minimal pipeline that you can customize to build and deploy your code.
# Add steps that build, run tests, deploy, and more:
# https://aka.ms/yaml

name: $(Date:yyyyMMdd)$(Rev:.r)_$(SourceBranchName)

pool:
  vmImage: ubuntu-20.04

stages:
  - stage: Stage1
    displayName: "Stage 1: Job A depende de Job B"
    jobs:
      - job: jobA
        displayName: Job A
        dependsOn: jobB
        steps:
          - script: echo Este es el trabajo A
      - job: jobB
        displayName: Job B
        steps:
          - script: echo Este es el trabajo B
          - bash: |
              echo Hola mundo
              echo Hola España
          - pwsh: |
              Write-Host Hola mundo
              Write-Host Hola España
  - stage: Stage2
    displayName: "Stage 2: Job A, Job B independientes"
    jobs:
      - job: jobA
        displayName: Job A
        steps:
          - script: echo Este es el trabajo A
      - job: jobB
        displayName: Job B
        steps:
          - script: echo Este es el trabajo B
```

### Tasks y artifacts

Una `steps.task` es un bloque de código de una pipeline. 

- AZ Devops nos ofrece una catálago de tasks.
- AZ Devops dispone de un "wizard" para incorporar las tasks al código YAML
- El número tras `@` hace referencia a la versión de la task.

Algunas de las tasks más utilizadas son las relacionadas con la generación y publicación de `artifacts`.

Un `artifact` es un componente desplegable de tu aplicación.

Las tasks `PublishPipelineArtifact@1` y `DownloadPipelineArtifact@2` se utilizan para publicar y descargar artefactos.

La variable predefinida `$(build.artifactstagingdirectory)` almacena la ruta de acceso local en el agente donde se copian los artefactos antes de ser pusheados a su destino. Este directorio se purga solo antes de cada build.

En 2022 se recomienda usar `PublishPipelineArtifact@1` y `DownloadPipelineArtifact@2` en lugar de `PublishBuildArtifacts@1` y `DownloadBuildArtifacts@0` respectivamente. 

# Módulo pipelines CD

Vamos a hacer un despliegue de una aplicación `.NET CORE` a una `Azure Web Service`.

## Crear una release

Repositorio del laboratorio: `lab0901-pipelines-dotnet-core`.

### Crear repositorio

Se clona en AZ devops el repo [MicrosoftDocs/pipelines-dotnet-core.git](https://github.com/MicrosoftDocs/pipelines-dotnet-core.git)

Se crea la siguiente pipeline:

```yaml
trigger:
- master

pool:
  vmImage: ubuntu-latest

variables:
 Parameters.RestoreBuildProjects : '**/*.csproj'
 Parameters.TestProjects: '**/*.csproj'
 BuildConfiguration: 'Release'

steps:
- task: DotNetCoreCLI@2
  displayName: Restore
  inputs:
    command: restore
    projects: '$(Parameters.RestoreBuildProjects)'

- task: DotNetCoreCLI@2
  displayName: Build
  inputs:
    projects: '$(Parameters.RestoreBuildProjects)'
    arguments: '--configuration $(BuildConfiguration)'

- task: DotNetCoreCLI@2
  displayName: Test
  inputs:
    command: test
    projects: '$(Parameters.TestProjects)'
    arguments: '--configuration $(BuildConfiguration)'

- task: DotNetCoreCLI@2
  displayName: Publish
  inputs:
    command: publish
    publishWebProjects: True
    arguments: '--configuration $(BuildConfiguration) --output $(build.artifactstagingdirectory)'
    zipAfterPublish: True

- task: PublishBuildArtifacts@1
  displayName: 'Publish Artifact'
  inputs:
    PathtoPublish: '$(build.artifactstagingdirectory)'
    ArtifactName: 'drop'
    publishLocation: 'Container'
  condition: succeededOrFailed()
```

Notas de las tasks:

- `DotNetCoreCLI@2` para compilar, probar, empaquetar o publicar una aplicación `.NET CORE`
- `PublishBuildArtifacts@1` para publicar artifacts

Podemos navegar hasta el artefacto publicado utilizando el enlace situado en el resumen de la ejecución de la pipeline, como se muestra en la Figura ['Artifacts published'](fig).

![Artifacts published](./images/Artifacts-published.PNG)

### Crear entornos DEV y PRO en Azure

Se supone que se puede hace gratis (hasta 10 aplicaciones). Vamos a crear dos recursos de  `Web App`, uno para el entorno `DEV` y otro para `PRO`.

Seguir en Azure los siguientes pasos:

1. Pasos en Azure para crear una `Web App` para el entorno `DEV`:
  - Crear un grupo de recursos para alojar la `Web App`.
  - Crear el recurso `Web App` .
  - Incluir `DEV` en el nombre del recurso.
  - Hay que tener en cuenta que, en nuestro caso, es una aplicación `.NET Core`.
  - En el mismo sitio, se crea un `App Service Plan`.
  - Se escoge la opción `Free`.
  - Se deshabilita la opción `Enable Application Insight` (por si acaso tiene costes)
2. Idem anterior para el entorno `PRO` utilizando el mismo `App Service Plan` creado en el paso anterior.

Si entramos en el recurso de una `Web Service`, se muestra la url para navegar hasta ella. Antes del despliegue, la web no tiene contenido y se muestra lo que aparece en la Figura ['Web App on DEV'](fig)

![Web App on DEV](./images/Web-App-on-DEV.PNG)

Tras crear la Release Pipeline y realizar el deploy, se verá lo que muestra la Figura ['Web App on DEV. Deployment'](fig)

![Web App on DEV. Deployment](./images/Web-App-on-DEV-Deployment.PNG)

### Construir la Release Pipeline con el stage DEV

Es importante distinguir y no confundir los dos conceptos siguientes:

- `Release Pipeline` Es la pipeline que conduce la release. Se crea, o más bien se construye, "una sola vez". La opción en AZ Devops se llama `New Release Pipeline`.
- `Release` Es la release en si misma. Se crea cada vez que se quiere hacer un despiegue. La opción en AZ Devops se llama `Create (new) release` . Tras crear una Release se suele hace un `Deploy` (`Deploy Stage` o `Deploy multiple`)

En la pestaña `Pipelines - Releases` , se utiliza la opción `New Release Pipeline` . 

Una `Release Pipeline` consta de `Artifacts` y `Stages`. Como mínimo la Release Pipeline debe contener un artefacto y un stage.

![Release pipeline. Artifacts and stages](./images/Release-pipeline-Artifacts-and-stages.PNG)

Hay dos pestañas fundamentales. La primera es la pestaña `Pipeline`, que muestra el esquema gráfico de la pipeline, ver la Figura ['Release pipeline. Artifacts and stages'](fig). También permite el acceso mediante iconos a las siguientes opciones:

- Artifacts - `Schedule release trigger`
- (For each) `Artifact - Continuous deployment trigger`
- (For each) `Stage - Pre-deployment conditions`
- (For each) `Stage - Post-deployment conditions`

Y la segunda es la pestaña `Tasks`, donde se configuran las tasks de los distintos Stages.

El resto de pestañas las vamos a dejar con los valores por defecto.

#### Añadir el Stage DEV

En nuestra práctica, vamos a configurar un stage llamado `DEV` (Trigger: After Release) que va a constar de la tarea `Azure App Service deployment`; se utiliza la template del mismo nombre.

![Azure app service deployment](./images/Azure-app-service-deployment.png)

Para que la task funcione, hay que hacer la conexión a Azure mediante un `Azure service connection` como se muestra en la Figura ['Configure an Azure service connection'](fig). Una vez hecho, usaremos la misma conexión si creamos un nuevo Stage.

![Configure an Azure service connection](./images/Configure-an-Azure-service-connection.PNG)

Se puede ver la configuración completa de la task en la Figura ['Release pipeline. Deploy AZ App Service'](fig).

![Release pipeline. Deploy AZ App Service](./images/Release-pipeline-Deploy-AZ-App-Service.PNG)

En este punto podríamos añadir más tasks dentro del mismo Stage.

#### Añadir un artifact

Hay varios tipos de fuente que podemos utilizar para añadir un artifact. Se muestran en la Figura ['Release pipeline. Add an artifact'](fig) . Como nosotros tenemos una `Build Pipeline` mediante la cual generamos el artefacto, seleccionamos la opción `Build`

![Release pipeline. Add an artifact](./images/Release-pipeline-Add-an-artifact.PNG)

En la Figura ['Release pipeline. Add an artifact 2'](fig) se muesta la configuración del artefacto. Observar que AZ Devops detecta que ya hemos ejecutado la pipeline que genera el artefacto de nombre `drop`.

![Release pipeline. Add an artifact 2](./images/Release-pipeline-Add-an-artifact-2.PNG)

En la Figura ['Release pipeline. CD trigger'](fig) se muestra como activar el trigger de despliegue continuo (CD)

![Release pipeline. CD trigger](./images/Release-pipeline-CD-trigger.PNG)

El la Figura ['Release pipeline. Save'](fig) se muestra el resultado final de la `Release pipeline`, tras añadir los artifacts y stages deseados. Se finaliza haciendo un `save`. 

![Release pipeline. Save](./images/Release-pipeline-Save.PNG)

### Crear la Release y hacer el deploy

Tras guardar la Release Pipeline, hay que hacer un `Create Release`.

En el caso de que hayamos cerrado ventanas, navegamos a `Pipelines - Releases`, buscamos la `Release Pipeline` que nos interesa y utilizamos la opción `Create release`. Ver Figura ['Create release'](fig).

![Create Release](./images/Create-Release.PNG)

Hay varias formas para ejecutar el `Deploy`. En la Figura ['Create Release. Deploy'](fig) se muestra una de ellas.

![Create Release. Deploy](./images/Create-Release-Deploy.PNG)

Por último, se indican las opciones que correspondan y se lanza la Release. Ver Figura ['Create release. Deployment options'](fig).

![Create Release. Deployment options](./images/Create-Release-Deployment-options.PNG)

### Probar el flujo completo de CI/CD

Para probar el flujo completo de CI/CD, lo único que tenemos que hacer es modificar un archivo del repositorio. Para que el cambio tenga un impacto a nivel gráfico sobre la App Service levantada en Azure, vamos a modicar el archivo `./Views/Home/Index.cshtml` editando p.e. la etiqueta `h1`. 

```html
@{
    ViewData["Title"] = "Home Page";
}

<div class="text-center">
    <h1 class="display-4">Curso de Azure Devops</h1>
    <p>Learn about <a href="https://docs.microsoft.com/aspnet/core">building Web apps with ASP.NET Core</a>.</p>
</div>
```

Flujo tras el cambio en la rama `master`:

- Se dispara la `Build Pipeline` <-- `trigger: master`
- Se dipara la `Release` 
  - Artifact <-- `CD trigger: enabled` (every time a new build is available)
  - Se ejecuta el Stage `DEV` <-- `Trigger: After release`

Nombres de las pipelines:

- Build pipeline: `Azure-App-Service PUBLISH ARTIFACT` genera un artefacto
- Release pipeline: `01 - Azure-App-Service DEPLOYMENT`

Notas:

- No se  que configuración utilicé, que la `Build Pipeline` también se disparaba con independencia de que estuviera o no estuviera el `trigger: master`.

Posibles errores:

> Error: No package found with specified pattern: `D:\a\r1\a\**\*.zip` Check if the package mentioned in the task is published as an artifact in the build or a previous stage and downloaded in the current job.

### Editar la Release Pipeline añadiendo el stage PRO

Añadimos un nuevo stage, el de `PRO` a la `Release Pipeline`. En este caso se selcciona un `Trigger: Manual only` como se observa en la Figura ['Release pipeline. New Stage. Manual only'](fig).

![Release pipeline. New Stage. Manual only](./images/Release-pipeline-New-Stage-Manual-only.PNG)

En la Figura ['Release pipeline. New Stage. Manual only vs After release'](fig) se observa que si el trigger es de tipo `After release`, entonces se refleja gráficamente en el esquemas de la pipeline mediante una línea que conecta el Stage correspondiente con la caja de `Artifacts`

![Release pipeline. New Stage. Manual only vs After release](./images/Release-pipeline-New-Stage-Manual-only-vs-After-release.PNG)

### Crear una nueva Release (de la misma Release Pipeline)

La Release Pipile que hemos construído, tiene dos Stages:

- `DEV` <-- `Trigger: After release`
- `PRO` <-- `Trigger: Manual only`

Creamos una nueva release con la opción `Create release` y observamos que solo se ejecuta el Stage `DEV` (el `deploy` del Stage `PRO` se tiene que ejecutar a mano).

Como se observa en la Figura ['Create Release. Trigger Change'](fig), existe la posibilidad, en el momento de lanzar la Release, de modificar el Trigger del Stage `DEV` y cambiarlo a `Manual`.

![Create Release. Trigger Change](./images/Create-Release-Trigger-Change.PNG)

Tras crear la Release, la situación es la de la Figura ['Azure app service deployment. Releases'](fig), donde se observa que solo se ha hecho el despliegue en el entorno `DEV`.

![Azure app service deployment. Releases](./images/Azure-app-service-deployment-Releases.png)

### Hacer el deploy del stage PRO

Se navega a `Pipelines - Releases`, se busca la Release que nos interesa y se navega a los sitios desde los cuales se puede hacer el deploy de un Stage en particular, en este caso del Stage `PRO`. Es bastante intuitivo encontrar el boton `Deploy`.

Por último se navega a los entornos de `DEV` y `PRO` (urls en Azure), para comprobar que se ha desplegado correctament.

### Algunas conclusiones y propuestas de I+D

Ventajas de este flujo de trabajo:

- Es el mismo artefacto (aplicación) el que fluye de un entorno a otro.
- La aplicación está igual en todos los entornos.
- Solo cambia la configuración y los secretos.

Líneas de I+D:

- `Pre-deployment conditions` de un Stage
- `Post-deployment conditions` de un Stage

## Variables de entorno

Repositorio del laboratorio: `lab0901-pipelines-dotnet-core`.

Como ya se ha dicho, en el flujo de trabajo, es el mismo artefacto (código de la aplicación) el que se despliega a `DEV` y `PRO`, sin embargo, hay configuraciones y valores de variables y secretos que pueden cambiar entre entornos. Para ello se utilizan las variables de entorno.

### Crear grupo de variables

En la pestaña `Pipelines - Library`, creamos dos grupos de variables, uno para cada entorno de despliegue.

- `Azure-App-Service-DEV`
- `Azure-App-Service-PRO`

Ambos grupos van a tener las mismas variables (utiliza el clonado, por rapidez) pero con distintos valores. Para hacer pruebas, se crean las variables `connectionString` y `reintentos`. Para utilizarlas en la Release Pipeline, se utilizará la sintaxis habitual, es decir se utilizará `$(connectionString)` y `$(reintentos)` respectivamente.

### Modificar el archivo de configuración del repositorio

Investigar este paso. ¿Qué repercusiones tiene?

- Modificamos el archivo de configuración de nuestra aplicación editando el archivo `appsettings.json`

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ConnectionString": "",
  "Reintentos": 1
}
```

### Configurar variables en una Release Pipeline

En una `Release Pipeline` se pueden utilizar los siguientes tipos de variables:

- `Pipeline variables` Específicas para la pipeline.
- Variables de los `Variable groups` El grupo suele ser para un entorno específico (DEV, PRO, etc).
- `Predefined variables` Consultar la documentación oficial.

En la Figura ['Release pipeline. Variables'](fig) se observa el tipo de variables que se pueden utilizar. Las `Pipeline variables` se definen construyendo/editando la Release Pipeline. 

![Release pipeline. Variables](./images/Release-pipeline-Variables.png)

Para utilizar las variables de un grupo (definidas en la `Library`) hay que hacer un `Link variable group` como se muestra en la la Figura ['Release pipeline. Link variable group'](fig). La idea es que el grupo de variables creada para el entorno `DEV` se vincula con el Stage `DEV` y lo mismo para cada uno de los entornos/stages.

![Release pipeline. Link variable group](./images/Release-pipeline-Link-variable-group.PNG)

### Utilizar las variables en una Release Pipeline

Paso para utilizar las variables de los grupos vinculados:

- Se edita la Release Pipeline.
- Los siguiente pasos de hacen para cada stage/entorno.
- Nos situamos en la pestaña `Tasks`.
- Seleccionamos el `task` y el `stage` deseados.
- En este caso la task es una `Deploy Azure App Service`
- Navegamos a la opción `App settings`.
- Se utiliza la opción tres puntos para introducir las variables como clave-valor.
- Ver la Figura ['Release pipeline. Task App settings'](fig)

![Release pipeline. Task App settings](./images/Release-pipeline-Task-App-settings.PNG)

Tras hacer el deployment en cada uno de los stages/entornos, se puede navegar al recurso de Azure correspondiente a cada entorno (`DEV`, `PRO`) y en la pestaña `Settings - Configuration` del recurso comprobar los valores de las variables. Serán distintos en cada uno de los recursos/entornos porque así hemos querido que sea. Ver la Figura ['Azure app service. Settings configuration in Azure'](fig)

![Azure app service. Settings configuration in Azure](./images/Azure-app-service-Settings-configuration-in-Azure.png)


## Rollback

Un `rollback` (retroceso) es un `deploy` de una release antigua.

Tiene que existir un buen motivo para hacerlo y hay que analizar bien lo que se está haciendo porque puede implicar cambios no deseado en el entorno sobre el que se hace.

Las figuras siguientes muestran lo que hemos hecho en nuestra práctica.

La Figura ['Releases before the rollback'](fig) muestra el estado de las releases antes del rollback. Observar que:

- El último despliegue (Currently deployed) a `DEV` es el de la `Release 18`.
- El último despliegue (Currently deployed) a `PRO` es el de la `Release 17`.
- Ha habido despliegues (Deployed) a `DEV` en las releases `16` y `18`.
- Ha habido despliegues (Deployed) a `DEV` en las releases `15` y `17`.

![Releases before the rollback](./images/Releases-before-the-rollback.png)

Lo que vamos a hacer, partiendo del estado mostrado, es el `Deploy` a `DEV` de la `Release 16` (To be deploy) , lo que implica `Rolling back changes` (reversion de cambios), como nos indica el aviso que se muestra en la Figura ['Deploy release. Rollback'](fig).

![Deploy release. Rollback](./images/Deploy-release-Rollback.png)

La Figura ['Releases after the rollback'](fig) muestras el estado de las releases tras el rollback.

![Releases after the rollback](./images/Releases-after-the-Rollback.png)

# Estrategias de despliegues

## Tipos de estrategias de despliegues

- Bule-green deployments
- Canary releases
- Dark launching
- A/B testing
- Progressive exposure or ring-based deployment
- Feature toggles

## Blue-Green

Consultar [¿Qué es la implementación azul-verde?](https://www.redhat.com/es/topics/devops/what-is-blue-green-deployment)

Una implementación blue-green es un modelo de lanzamiento de aplicaciones que transfiere poco a poco el tráfico de usuarios de cierta versión anterior de una aplicación o microservicio a una versión nueva casi idéntica, cuando ambas se encuentran en producción.

Es una técnica que reduce el riesgo y el tiempo de inactividad:

- `Entorno azul` identifica la versión antigua
- `Entorno verde` identifica la versión nueva

## Feature togles o feature flags

Consultar [Beneficios De Las Feature Toggles O Feature Flags](https://apiumhub.com/es/tech-blog-barcelona/beneficios-feature-toggles-feature-flags/) y [Continuously deliver with dark launches and feature toggles](https://www.ibm.com/garage/method/practices/run/practice_dark_launch_feature_toggles/)

Las `feature toggles` o `feature flags` te permiten conmutar una funcionalidad de on a off en cualquier momento, incluso tras haber desplegado tu código. Permiten a los equipos de desarrollo modificar el comportamiento de un sistema sin cambiar el código. 

Las feature toggles son principalmente variables que se usan dentro de declaraciones condicionales. Se usa para añadir nuevas funcionalidades a una aplicación que pueden ser activadas/desactivadas.

Ventajas:

- Invisibilidad (hasta que se activa)
- Velocidad (CI/CD)
- A/B testing 
- Flexibilidad
- Seguridad
- Reducción del riesgo
- Actualizar las funcionalidades que ya están en vivo

Tipos:

- `Release togle` Poner en cuarentena una funcionalidad inacabada.
- `Ops togle` Funcionalidad con impacto desconocido en el PRO.
- `Experiment togle` Permite ejecutar un A/B testing
- `Permissioning togle` Cambiar funcionalidades a ciertos usuarios.

## Canary releases

Consultar [¿Qué es un lanzamiento tipo canary?](https://www.jetbrains.com/es-es/teamcity/ci-cd-guide/concepts/canary-release/)

Una `canary release `es una estrategia de implementación destinada a lanzar los cambios iniciales a un pequeño subgrupo de usuarios. Es una forma de identificar problemas potenciales lo antes posible sin exponer a todos los usuarios finales, del mismo modo que el canario que acompañaba a los mineros en las minas de carbón, ante la exposición a gases tóxicos, moría antes que un minero, dándole tiempo a este a escapar.

Es una combinación de:

- `Feature toggles` activar/desactivar la nueva funcionalidad.
- `Traffic routing` enrutar trafico (con la nueva funcinalidad) a ciertos sitios.
- `Despliegues en slots`

La herramienta `Traffic Manager` de Azure se utiliza para dirgir el tráfico de carga. Se trata de un equilibrador de carga de tráfico basado en DNS. Permite distribuir el tráfico a los servicios de manera óptima y proporcionando alta disponibilidad y capacidad de respuesta. Se configura por prioridad, ponderado, rendimiento, geográfico, multivalor, subred.

Consultar [Nested Traffic Manager profiles](https://docs.microsoft.com/en-us/azure/traffic-manager/traffic-manager-nested-profiles).

Consultar:

- [¿Qué es un ''entry point'' y un ''end point''?](https://es.stackoverflow.com/questions/51758/qu%C3%A9-es-un-entry-point-y-un-end-point).
- [¿Me podrían ayudar a diferenciar que es un endpoint y una API?](https://es.stackoverflow.com/questions/343196/me-podr%c3%adan-ayudar-a-diferenciar-que-es-un-endpoint-y-una-api?noredirect=1&lq=1)

## Dark launching

Comnsultar [What Is A Dark Launch?](https://devcycle.com/solutions/dark-launch)

Es muy parecido a la `Canary Release`. La diferencia es que aquí estas buscando la respuesta de los usuarios a las nuevas funciones de su interfaz, en lugar de probar el rendimiento del backend.

Se denomina oscuro porque los usuarios de prueba no son conscientes de que son usuarios de prueba.

## A/B testing

Consultar [What is A/B testing?](https://docs.microsoft.com/en-us/learn/modules/implement-test-progressive-exposure-deployment/2-what-a-b-testing)

Un `A/B testing` compara dos versiones de una página web o aplicación entre sí para determinar cual funciona mejor.

## Despliegue en anillos

Consultar: 
- [Use deployment rings with extension releases](https://docs.microsoft.com/en-us/azure/devops/migrate/phase-rollout-with-rings?view=azure-devops)
- [Deploying new releases: Feature flags or rings?](https://opensource.com/article/18/2/feature-flags-ring-deployment-model)

En un despliegue en anillos, se hace un despliegue gradual validando los cambios de tu extensión en producción imentras se limita el número de usuarios afectados.

![Ring based deployment](./images/Ring-based-deployment.png)

# Módulo Artifacts

## ¿Qué es Azure Artifacts?

Es el gestor de paquetes de AZ Devops.

Con `AZ Artifacts` se puede crear y compartir, a partir de orígenes públicos y privados, fuentes de paquetes de:

- `Maven` SPM (Software Project Management) y CT (Comprehension Tool) para `Java`. Basado en el concepto de `POM` (Project Object Model).
- `NPM` gestor de paquetes por defecto para `Node.js` (JavaScript).
- `NuGet` gestor de paquetes para `.NET`
- `Python`
- `Universal Packages`

## Artifacts Feed. Crear feed

Los `Artifacts Feeds` son constructos organizativos que permiten almacenar, gestionar y agrupar tus paquetes y controlar con quien los compartes.

Hay dos tipos de feed:

- `Project-scoped feed` De ámbito el proyecto
- `Organization-scoped feed` De ámbito la organización

En el pasado, todos los feeds formaban parte del ámbito de la organización. Se accedía a ellos desde cualquier proyecto interno de la organización. Los `Project-scoped feed` surgen para que exista un tipo de feed que se pueda hacer público (compartir paquetes en internet).

El feed de nuestra orgqanización viene creado por defecto.

Desde la pestaña `Artifacts`, podemos crear un feed de poryecto con la opción `Create Feed`. En nuestr casi, creamos el feed `Prueba`. Una vez creado, podemos configurarlo utilizando el icono de settings, como se muestra en la Figura ['Artifact Feed setttings'](fig).

![Artifact Feed setttings](./images/Artifacts-Feed-settings.png)

En la Figura ['Artifact Feed setttings. Upstream sources'](fig), se observan las distintas pestañas con opciones de configuración,con más detalle, la pestaña de las fuentes trackeadas (Upstream sources).

![Artifact Feed setttings. Upstream sources](./images/Artifacts-Feed-settings-Upstream-sources.png)

## Conectar feed

En la pestaña `Artifacts`, nos situamos en el feed deseado y hacemos un `Connect feed`. En la Figura ['Artifacts. Connect to feed'](fig) se muestran las opciones  de conexión que se pueden utilizar.

![Artifacts. Connect to feed](./images/Artifacts-Connect-to-feed.png)

En el curso se muestra un ejemplo de conexión con `Visual Studio`

## Lab: crear librería que se sube versionada a Artifacts y se consume en otro proyecto

[PENDIENTE](todo)









