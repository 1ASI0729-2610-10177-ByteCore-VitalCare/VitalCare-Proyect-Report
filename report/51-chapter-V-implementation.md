# Capítulo V: Product Implementation, Validation & Deployment

## 5.1. Software Configuration Management

### 5.1.1. Software Development Environment Configuration

A continuación, se describen los productos de software empleados en el desarrollo del proyecto. Esta sección tiene como objetivo facilitar la comprensión y continuidad
del trabajo a los actuales y futuros desarrolladores, asegurando una colaboración efectiva a lo largo del ciclo de vida del producto digital.

**Project Management**
- Trello – https://trello.com/<br>
  Se ha utilizado Trello como herramienta principal de gestión de tareas. Esta plataforma permite visualizar el progreso de cada etapa del proyecto mediante
  tableros personalizables, facilitando la organización de pendientes, tareas en desarrollo y actividades finalizadas. Además, su interfaz intuitiva y accesibilidad
  desde cualquier navegador con una cuenta registrada la convierten en una solución ágil para el seguimiento de proyectos en equipo.

**Requirements Management**
- Google Docs – https://docs.google.com/<br>
  Para la redacción, gestión y revisión de los requisitos del sistema se ha empleado Google Docs. Su funcionalidad de edición colaborativa en tiempo real ha
  permitido que todos los integrantes del equipo puedan aportar, comentar y revisar los documentos desde cualquier dispositivo.

**Product UX/UI Design**
- Figma – https://www.figma.com/<br>
  Figma ha sido fundamental para el diseño de interfaces y la creación de prototipos interactivos. Permite que varios usuarios trabajen simultáneamente en los
  wireframes y mockups, lo que ha facilitado una comunicación más eficiente entre el equipo de diseño y desarrollo.
- Miro https://miro.com/es/<br>
  Pizarra digital colaborativa utilizada para sesiones de Big Picture EventStorming y Design-Level EventStorming, facilitando la identificación de Bounded Contexts, Events, Commands y Aggregates del dominio.
- LucidChart https://www.lucidchart.com/pages/es <br>
  Aplicación de diagramación colaborativa para la creación de Wireflows, User Flows, diagramas UML (Class Diagrams) y Database Diagrams de la arquitectura del software.

**Software Development**
- Landing Page y Frontend (HTML, CSS, JS) – https://www.jetbrains.com/webstorm/<br>
  Desarrollada con HTML5, CSS3 y JavaScript. El entorno de desarrollo fue IntelliJ Webstorm por sus herramientas avanzadas de depuración y control de versiones.
  Web Services (Spring Boot) – https://www.jetbrains.com/idea/
  Desarrollado en Spring Boot Framework con el lenguaje de programación Java , usando IntelliJ IDEA como entorno de desarrollo. Se requiere el Java Development Kit (JDK) versión 17 o superior (o la versión indicada por el docente) disponible en https://www.oracle.com/java/technologies/downloads/.

**Software Documentation**
- Google Docs y GitHub README <br>
  La documentación del software se ha centralizado en Google Docs. El archivo README en GitHub incluye instrucciones de despliegue, estructura del repositorio y
  requerimientos técnicos.
- Markdown https://www.markdownguide.org/ <br>
  Lenguaje de marcado ligero para la elaboración del Project Report en el repositorio GitHub. Permite estructurar documentación con formato consistente y compatible con control de versiones.

## Deployment & Hosting

### **GitHub Pages**
**Descripción**:
Es un servicio de alojamiento de sitios estáticos que procesa archivos HTML, CSS y JavaScript directamente desde un repositorio en GitHub para la publicación de aplicaciones web.

**Uso**:
Se utiliza para el despliegue de la **Landing Page** y la aplicación frontend desarrollada con el framework **Angular**. El proceso se integra con el flujo de trabajo de Git, donde la rama de producción (`main` o `gh-pages`) se sincroniza automáticamente para actualizar el sitio. Esto permite una distribución eficiente de la interfaz de usuario, garantizando que los cambios en el código se reflejen de manera inmediata en el entorno de producción bajo un protocolo seguro HTTPS.

**Descripción**:
Plataformas PaaS (Platform as a Service) diseñadas para el despliegue de aplicaciones robustas del lado del servidor, con soporte nativo para entornos de ejecución como Java.

**Uso**:
Se emplea para el despliegue de los **Web Services** desarrollados con **Spring Boot**. A diferencia de los sitios estáticos, estas plataformas permiten la ejecución del Java Development Kit (JDK) y la conectividad con sistemas de gestión de bases de datos relacionales, asegurando que la API RESTful esté disponible de manera persistente para ser consumida por el frontend alojado en GitHub Pages.

### 5.1.2. Source Code Management

Para el seguimiento y control de modificaciones en el código fuente, el equipo utiliza **GitHub** como plataforma principal, organizada bajo la organización oficial **1ASI0729-2610-10177-ByteCore-VitalCare**.

Se aplica **GitFlow** como flujo de trabajo (*workflow*) de control de versiones, **Conventional Commits** para la estandarización de los mensajes de confirmación y **Semantic Versioning** para la gestión de versiones y lanzamientos (*releases*).

A continuación, se detallan los repositorios que conforman la solución técnica de **VitalCare**:

| Producto | Repositorio |
| :--- | :--- |
| **Project Report** | [https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Proyect-Report.git](https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Proyect-Report.git) |
| **Landing Page** | [https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Landing-Page.git](https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Landing-Page.git) |
| **Frontend Web Application** | [https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Frontend.git](https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Frontend.git) |
| **Web Services** | [https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Backend.git](https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Backend.git) |

#### **GitFlow Workflow**
El equipo implementa GitFlow para organizar el desarrollo. Las ramas se clasifican de la siguiente manera:

* **Ramas principales:**
    * `main`: Contiene el código fuente en un estado estable y listo para producción. Solo se actualiza mediante fusiones (*merges*) de ramas de *release*.
    * `develop`: Rama de integración donde se consolidan las funcionalidades terminadas antes de pasar a producción.
* **Ramas de soporte:**
    * `feature/<nombre>`: Ramas temporales creadas desde `develop` para el desarrollo de funcionalidades específicas o secciones del informe (ej. `feature/chapter-1`). Al finalizar, se fusionan de vuelta a `develop`.
    * `release/<version>`: Ramas de preparación para un lanzamiento oficial, permitiendo realizar ajustes finales y pruebas de integración antes de fusionar a `main`.

#### **Conventional Commits**
Los mensajes de confirmación (*commit*) siguen la estructura: `<type>(scope): description`. Los tipos permitidos incluyen `feat` (funcionalidad), `fix` (corrección), `docs` (documentación), `style` (formato), `refactor` (mejora de código) y `chore` (mantenimiento).

### 5.1.3. Source Code Style Guide & Conventions

En este apartado se definen los estándares de codificación y nomenclatura adoptados por el equipo para garantizar la mantenibilidad y legibilidad del código de **VITAL CARE**. Se aplican las siguientes convenciones basadas en las guías de estilo de Google:

- **Language Standards**: Todo el código fuente, incluyendo nombres de variables, funciones, clases, IDs de CSS y comentarios, se redacta exclusivamente en idioma **inglés** para mantener un estándar profesional global.

- **Naming Conventions**:
    - **Backend (Java / Spring Boot)**: Se utiliza `PascalCase` para nombres de clases y `camelCase` para métodos, variables locales y parámetros (ej. `VitalSignController`, `getPatientById`). Se sigue la Google Java Style Guide.
    - **Frontend (HTML/CSS)**: Se utiliza `kebab-case` para nombres de archivos de estilo y para clases e IDs en las hojas de estilo (ej. `.patient-card`, `.alert-banner`). Se siguen las guías Google HTML/CSS Style Guide y HTML Style Guide and Coding Conventions de W3Schools.
    - **TypeScript / Angular**: Se aplica `camelCase` para variables y funciones, y `PascalCase` para componentes y servicios (ej. `PatientListComponent`, `AlertService`). Se siguen la Angular coding style guide y la Google TypeScript Style Guide.

- **Source Control Conventions**: Se aplica el estándar de **Conventional Commits**, utilizando prefijos descriptivos en inglés como `feat:`, `fix:`, `docs:`, `style:`, `refactor:` y `chore:` para asegurar un historial de versiones estructurado y rastreable.

- **Code Formatting**: Se mantiene una indentación consistente de 2 espacios en archivos HTML, CSS y TypeScript siguiendo las convenciones de Angular. En el desarrollo backend con Java se sigue el formato automático de IntelliJ IDEA para mantener la limpieza y consistencia de los archivos de clase.

- **Gherkin**: Los criterios de aceptación de los User Stories se redactan siguiendo las convenciones de Gherkin Conventions for Readable Specifications para garantizar especificaciones legibles y comprobables.

### 5.1.4. Software Deployment Configuration

Esta sección detalla la configuración del despliegue de la solución, permitiendo que los productos digitales sean accesibles de forma continua en un entorno de producción.

- **Hosting & Cloud Platforms**:
    - **Landing Page**: Se ha desplegado satisfactoriamente en **GitHub Pages**, aprovechando su integración nativa con los repositorios de GitHub y su soporte para sitios estáticos bajo protocolo HTTPS.
    - **Frontend Web Application**: Se ha definido el despliegue en **GitHub Pages** mediante el build de producción generado por Angular (`ng build`), publicando el contenido de la carpeta `dist/` en la rama de producción.
    - **Web Services & API**: Para las fases posteriores del proyecto, se definirá el proveedor de despliegue para los servicios web desarrollados en Spring Boot, garantizando la disponibilidad persistente de la API RESTful para ser consumida por el frontend.
- **Continuous Deployment (CD) Pipeline**:
    - **Integración**: El repositorio oficial en GitHub (`VitalCare-Landing-Page`) está vinculado directamente a GitHub Pages como plataforma de despliegue.
    - **Branching Strategy**: La rama `main` actúa como la rama de producción oficial. Cualquier cambio integrado mediante *merge* o *push* en esta rama activa automáticamente un nuevo despliegue hacia la URL pública: [https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/](https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/)
- **Environment Configuration**:
    - **Estado Actual (Sprint 1)**: El despliegue actual no requiere el uso de variables de entorno ni claves de API externas, dado que corresponde al despliegue de la Landing Page como prototipo visual e informativo desarrollado con HTML5, CSS3 y JavaScript.
    - **Planificación Futura**: En los próximos Sprints, se configurarán variables de entorno para gestionar de forma segura las cadenas de conexión a la base de datos MySQL y los tokens de autenticación requeridos por los servicios IoT del dispositivo parche.

---

## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1. Sprint 1

En este Sprint se desarrolló e implementó la primera versión
del Landing Page de VitalCare, incluyendo su despliegue
en un entorno accesible públicamente.

#### 5.2.1.1. Sprint Planning 1

A continuación se presenta el resumen del Sprint Planning Meeting
realizado para el Sprint 1.

| Sprint # | Sprint 1                                                                                                                                                                                                                                                                                                                                                      |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Sprint Planning Background** |                                                                                                                                                                                                                                                                                                                                                               |
| Date | 2026-04-15                                                                                                                                                                                                                                                                                                                                                    |
| Time | 04:30 PM                                                                                                                                                                                                                                                                                                                                                      |
| Location | Reunión virtual vía Google Meet                                                                                                                                                                                                                                                                                                                               |
| Prepared By | Rioja Nuñez, Franco Diego                                                                                                                                                                                                                                                                                                                                     |
| Attendees | HBardales Tejada, Luis Alexis / Caisahuana Osores, Becker Junior / Huaman Gallardo, Bruno Aldair / Rioja Nuñez, Franco Diego / Rocca Mariaca, Angel Mathias                                                                                                                                                                                                   |
| **Sprint Goal & User Stories** |                                                                                                                                                                                                                                                                                                                                                               |
| Sprint 1 Goal | Our approach focuses on strengthening VitalCare's digital presence by launching its initial landing page. We believe this will effectively communicate our value proposition to family members and seniors. This will be validated once the site is published on GitHub Pages, integrating strategic sections and calls to action targeted to both audiences. |
| Sprint 1 Velocity | 20                                                                                                                                                                                                                                                                                                                                                            |
| Sum of Story Points | 17                                                                                                                                                                                                                                                                                                                                                            |

#### 5.2.1.2. Aspect Leaders and Collaborators

En esta sección se detalla la matriz de liderazgo y colaboración (LACX) para el Sprint 1. Cada aspecto representa una fase crítica de la entrega, donde se designa un líder (L) responsable de la dirección del entregable y colaboradores (C) que apoyaron en su ejecución, cumpliendo con el objetivo de proporcionar liderazgo conjunto y un entorno colaborativo (ABET Student Outcome 3).

| Team Member (Last Name, First Name) | GitHub Username | Idea de Negocio y Bases | Landing Page | Diseño de App Web (Figma) | User Stories y Funciones | Análisis de Usuario y Needfinding |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| Rioja Nuñez, Franco Diego | FrancoDiegoR | **L** | C | C | C | C |
| Rocca Mariaca, Angel Mathias | MRMpro13 | C | **L** | C | C | C |
| Huaman Gallardo, Bruno Aldair | BrunoHG10 | C | C | C | **L** | C |
| Caisahuana Osores, Becker Junior | becker693 | C | C | **L** | C | C |
| Bardales Tejada, Luis Alexis | AlexisBardales | C | C | C | C | **L** |

#### 5.2.1.3. Sprint Backlog 1

<img src="assets/SprintBacklog.png" alt="SprintBacklog"/>

Enlace de Trello: https://trello.com/invite/b/69eab993248a35acb106f3a5/ATTId84e5c54d692b66f96b0986e5aa280133194A223/vitalcare

#### 5.2.1.4. Development Evidence for Sprint Review

Durante el Sprint 1, el equipo utilizó GitHub como sistema de control de versiones, siguiendo el flujo de trabajo GitFlow para asegurar una integración ordenada del código. A continuación, se presenta el registro de los commits más relevantes que evidencian el desarrollo de la Landing Page y la colaboración del equipo.

**Repository:** 1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Landing-Page

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `VitalCare-Landing-Page` | `main` | `7db1fbc` | `Delete .idea directory` | `Removed IDE configuration files from version control.` | 23/04/2026 |
| `VitalCare-Landing-Page` | `main` | `76a6b36` | `Merge pull request #2 from 1ASI0729-2610-10177-ByteCore-VitalCare/develop` | `Merged develop branch into main for Sprint 1 release.` | 23/04/2026 |
| `VitalCare-Landing-Page` | `develop` | `9b2ead9` | `feat(index): update title and add meta tags for SEO optimization` | `Updated page title and added description, keywords and author meta tags.` | 23/04/2026 |
| `VitalCare-Landing-Page` | `develop` | `bb8b0f0` | `feat(landing): Remove unused header, add animations, and fix image hero` | `Cleaned up unused elements, added scroll animations and fixed hero image rendering.` | 23/04/2026 |
| `VitalCare-Landing-Page` | `develop` | `416e484` | `feat(landing): add landing page structure and styles` | `Added full HTML structure and CSS styles for all landing page sections.` | 21/04/2026 |
| `VitalCare-Landing-Page` | `develop` | `be0110f` | `landing initial structure` | `Initial HTML and CSS structure for the landing page layout.` | 14/04/2026 |
| `VitalCare-Landing-Page` | `develop` | `4bd0d8b` | `Initial commit` | `Initial repository setup with base project files.` | 14/04/2026 |

#### 5.2.1.5. Execution Evidence for Sprint Review

En esta sección se presenta la evidencia de la ejecución del Sprint 1, demostrando el cumplimiento de los objetivos establecidos y el despliegue del producto en un entorno de producción accesible.

<img src="assets/Landing pAge EVIDENCE.png"/>

**Enlace del Landing Page:** [https://vitalcare.github.io/](https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/)

**Evidencia de Despliegue (GitHub Pages):**

A continuación, se presenta la captura del dashboard de GitHub que confirma el despliegue exitoso (Production Deployment) de la Landing Page desde el repositorio oficial de GitHub.

<img src="assets/Deploy Landing.png"/>

#### 5.2.1.6. Services Documentation Evidence for Sprint Review

Para el presente Sprint 1, el alcance se centró exclusivamente en la implementación y despliegue del Landing Page (sitio web estático). Por lo tanto, no se han desarrollado servicios RESTful API en esta etapa. La documentación detallada de los endpoints mediante OpenAPI (Swagger) se incluirá en los informes correspondientes a los siguientes Sprints, una vez iniciada la fase de implementación de los Web Services.

#### 5.2.1.7. Software Deployment Evidence for Sprint Review

Durante el Sprint 1, se realizó el despliegue de la Landing Page de VITAL CARE
utilizando GitHub Pages como plataforma de hosting. A continuación se describen
las actividades realizadas para lograr la publicación exitosa del sitio.

1. Se creó el repositorio `VitalCare-Landing-Page` bajo la organización
   `1ASI0729-2610-10177-ByteCore-VitalCare` en GitHub.

2. Se desarrolló la Landing Page en la rama `develop` siguiendo el flujo
   GitFlow, integrando las secciones de hero, problemática, beneficios,
   startup, planes y footer.

3. Una vez validado el contenido, se realizó el merge de `develop` hacia
   `main` mediante Pull Request, lo que activó automáticamente el despliegue
   en GitHub Pages.

4. Se verificó el despliegue exitoso accediendo a la URL pública:
   [https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/](https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/)

<img src="assets/Deploy Landing.png" />

#### 5.2.1.8. Team Collaboration Insights during Sprint

## Desarrollo del reporte

#### AV1:

<img src="assets/collabReport.png"/>

## Desarrollo de Landing Page
#### AV1:

<img src="assets/collabLanding.png" alt="Collab Landing Page"/>

---
## 5.2.2. Sprint 2

#### 5.2.2.1. Sprint Planning 2

A continuación se presenta el resumen del Sprint Planning Meeting
realizado para el Sprint 2.

| Sprint # | Sprint 2                                                                                                                                                                                                                                                                                                                                                      |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Sprint Planning Background** |                                                                                                                                                                                                                                                                                                                                                               |
| Date | 2026-05-10                                                                                                                                                                                                                                                                                                                                                    |
| Time | 04:30 PM                                                                                                                                                                                                                                                                                                                                                      |
| Location | Reunión virtual vía Google Meet                                                                                                                                                                                                                                                                                                                               |
| Prepared By | Rioja Nuñez, Franco Diego                                                                                                                                                                                                                                                                                                                                     |
| Attendees | HBardales Tejada, Luis Alexis / Caisahuana Osores, Becker Junior / Huaman Gallardo, Bruno Aldair / Rioja Nuñez, Franco Diego / Rocca Mariaca, Angel Mathias                                                                                                                                                                                                   |
| Sprint 2 – 1 Review Summary        | El sprint 1 estuvo muy bien coordinado; sin embargo, no cumplimos con los requisitos, lo que resultó en una disminución leve en la calidad del contenido. Los miembros del equipo están al tanto de estos errores gracias a la retroalimentación proporcionada por el Product Owner.                                                           |
| Sprint 2 – 1 Retrospective Summary | The team acknowledges that the previous sprint's development didn't fully align with the requested requirements. Fortunately, the Product Owner provided significant support through consistent feedback, enabling us to identify errors and make the necessary corrections to improve product quality. |
| **Sprint Goal & User Stories** |                                                                                                                                                                                                                                                                                                                                                               |
| Sprint 1 Goal | Our focus is on strengthening VitalCare's digital presence through the launch of our web application. We believe this will effectively communicate our value proposition to families dealing with challenges in monitoring patients who require constant care. |
| Sprint 1 Velocity | 20                                                                                                                                                                                                                                                                                                                                                            |
| Sum of Story Points | 17                                                                                                                                                                                                                                                                                                                                                            |


A continuación se presenta el resumen del Sprint Planning Meeting realizado para el Sprint 2.

| Sprint #                           | Sprint 2                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Sprint Planning Background**     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Date                               | 2026-05-11                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Time                               | 9:30 PM                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Location                           | Reunión virtual vía Discord                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Prepared By                        | Rioja Nuñez, Franco Diego                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Attendees                          | Herrera Enriquez, Diego Fernando / Mallqui Vilca, Dhilsen Armil / Rioja Nuñez, Franco Diego / Tufiño Argüelles, Luis Angel / Urviola Condori, Mateo Sebastián / Paredes Díaz, Tomás Alessandro                                                                                                                                                                                                                                                                                                   |
| Sprint 2 – 1 Review Summary        | Sprint 1 was very well coordinated; however, we failed to meet the requirements, resulting in a noticeable decrease in the quality of the content and the software product delivered during this sprint. The landing page was of good quality; however, the established requirements regarding commits and product development were not followed. Team members are aware of these errors thanks to feedback provided by the Product Owner.                                                       |
| Sprint 2 – 1 Retrospective Summary | The team admits that the development of the previous sprint was not fully aligned with the requested requirements. We recognize that the software products were correctly oriented in terms of the stated objectives; However, its implementation and development presented deficiencies. Fortunately, the Product Owner provided us with important support through constant feedback, which allowed us to identify errors and make the necessary corrections to improve the quality of the product. |
| **Sprint Goal & User Stories**     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Sprint 2 Goal                      | Our goal is to develop our first version of the frontend of our web application. We believe that this application will allow entity pharmacy administrators to manage data within the establishments belonging to the health entity, as well as its operators and devices. Likewise, operators will be able to manage the data received by the devices and transports according to the metrics received by them.                                                                                 |
| Sprint 2 Velocity                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Sum of Story Points                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |


#### 5.2.2.2. Aspect Leaders and Collaborators

#### 5.2.2.3. Sprint Backlog 2

<img src="assets/SprintBacklog2.png" alt="SprintBacklog2"/>

Enlace de Trello: https://trello.com/b/dNCMZ5xN/vitalcare-sprint-2

#### 5.2.2.4. Development Evidence for Sprint Review

Aquí se presentará el registro de commits de aplicación frontend durante el Sprint 2, evidenciando el desarrollo de funcionalidades relacionadas con la gestión de pacientes, historial médico, suscripciones y otros aspectos clave del sistema VitalCare.

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `VitalCare-Frontend` | `master` | `140b377` | `Add patient history model and vercel config` | `Added patient history model and Vercel deployment configuration.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `9a7836` | `Merge branch 'release/1.0.0' into master` | `Merged release/1.0.0 branch into master for version 1.0.0 release.` | 12/05/2026 |
| `VitalCare-Frontend` | `develop` | `c1870b` | `Merge branch 'origin/feature/suscription' into develop` | `Merged feature/suscription branch from remote into develop.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `54e119` | `feat: add patient history model and integrate into patient view` | `Added patient history model and integrated it into the patient view component.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `b7d1ea` | `Merge remote-tracking branch 'origin/feature/patients' into feature/patients` | `Merged remote tracking branch for feature/patients.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `3c5ddb` | `feat: add patient history model with loading and error states, update styles and layout` | `Added patient history model with loading/error states and updated component styles and layout.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `a2d4e2` | `chore: update mock data in db.json for subscriptions` | `Updated mock subscription data in db.json file.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `0c425b` | `feat: integrate main plans view and update application routes` | `Integrated main plans view component and updated application routing configuration.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `c940335` | `feat: create reusable plan-card component` | `Created a reusable plan-card component for displaying subscription plans.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `7829f80` | `feat: add facade service for subscription management` | `Added facade service to handle subscription management operations.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `d029ca9` | `feat: implement domain entities and http service for subscriptions` | `Implemented domain entities and HTTP service for subscription management.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `8138fa1` | `chore: update environment configuration and angular settings` | `Updated environment configuration and Angular project settings.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `ed6f6a2` | `agreed notifications 3` | `Updated notification configuration and settings.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `4972829` | `fix: remove placeholder files and clean code` | `Removed placeholder files and cleaned up code.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `d7065e5` | `feat: add patient model with form and photo upload` | `Added patient model with form component and photo upload functionality.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `babc644` | `fix: add missing modal location, expand the metrics for missing vital signs, add missing translation and clean code` | `Added missing modal, expanded metrics for vital signs, added missing translations and cleaned code.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `8b347e7` | `feat: add location management with assembler, entity, resource, and service` | `Added location management with assembler, domain entity, resource, and service layers.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `14e681e` | `feat: add vital signs model and related services for patient monitoring` | `Added vital signs model and related services for patient monitoring functionality.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `954f831` | `feat: implement patient management module with entity, service, and UI components` | `Implemented patient management module with domain entity, service, and UI components.` | 12/05/2026 |
| `VitalCare-Frontend` | `master` | `f5e46d3` | `feat: add initial application structure with routing and localization support` | `Added initial application structure with routing and i18n localization support.` | 10/05/2026 |
| `VitalCare-Frontend` | `master` | `8add6d1` | `initial commit` | `Initial repository setup with base project files.` | 09/05/2026 |

#### 5.2.2.5. Execution Evidence for Sprint Review

Aquí se muestran las funciones desarrolladas para esta entrega, algunas funciones fueron descartadas como el IAM por ser un módulo que se hará para la siguiente sprint

---

### Vista Home

<img src="assets/home-app-web.png" alt="Home app web"/>

### Vista Pacientes

<img src="assets/patients.png" alt="Patients app web"/>

### Vista planes de suscripción

<img src="assets/plans.png" alt="Plans app web"/>

### Vista notificaciones

<img src="assets/notifications.png" alt="Notifications app web"/>


#### 5.2.2.6. Services Documentation Evidence for Sprint Review

Durante el desarrollo del frontend de la aplicación, se decidió emplear JSON Server como una API simulada, debido a que el backend aún no se encontraba implementado. Esta herramienta permitió recrear el comportamiento de un servidor real, atendiendo solicitudes HTTP como GET, POST, PUT y DELETE mediante el uso de un archivo db.json que actuaba como base de datos persistente. Gracias a ello, fue posible continuar con la construcción, validación y prueba de los componentes y servicios del frontend de forma eficiente, manteniendo además una arquitectura desacoplada y preparada para integrarse posteriormente con el backend definitivo.

En este sprint, se documentaron y probaron distintos recursos utilizando JSON Server como fake API. Todos ellos soportan los métodos HTTP: GET, POST, PUT, PATCH, DELETE y OPTIONS.

| Recurso           | Registros existentes en db.json | Métodos HTTP Disponibles               |
|-------------------|---------------------------------|----------------------------------------|
| /notifications    | 3                               | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /users            | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /user_preferences | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /subscriptions    | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /patients         | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /patches          | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /vital_signs      | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /alerts           | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /support_tickets  | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |
| /locations        | 10                              | GET, POST, PUT, PATCH, DELETE, OPTIONS |

#### 5.2.2.7. Software Deployment Evidence for Sprint Review

En esta sección se mostrará la evidencia de ejecución de la primera versión de la aplicación web desplegada aen Vercel

---

### En esta sección se muestra el ingreso del repositorio en la app de Vercel

<img src="assets/evidence 1- sprint 2.png" alt="Deploy front 1"/>

### Aquí se muestra el proceso previo al despliegue de la aplicación web en Vercel

<img src="assets/evidence 2- sprint 2.png" alt="Deploy front 1"/>

### Aquí se muestra la aplicación ya desplegada en Vercel, con la URL pública para su acceso

<img src="assets/evidence 3- sprint 2.png" alt="Deploy front 1"/>

Enlace: https://vitalcarefrontend.vercel.app/home

#### 5.2.2.8. Team Collaboration Insights during Sprint
---

## 5.3. Validation Interviews

### 5.3.1. Diseño de Entrevistas
Estructura de Encuesta: VITAL CARE

¿Cuál es su nombre, edad y distrito donde reside?

¿A qué se dedica actualmente y a quién tiene a su cargo?

¿Cuánto tiempo lleva encargándose del cuidado o supervisión de la salud de su familiar?

¿Qué dispositivos utiliza habitualmente (Celular, PC, Tablet), qué sistema operativo tienen (Android, iOS, Windows) y qué navegador usa más (Chrome, Safari, Edge)?

Segmento objetivo 1: Adultos entre 25 y 50 años que cuidan familiares: El objetivo es medir el nivel de ansiedad por la falta de supervisión y la disposición a pagar por un sistema de alertas automáticas.

1.	¿Qué tan seguido se preocupa por el estado de salud de su familiar cuando no está con él/ella?
2.	¿Cómo se entera actualmente si su familiar tiene una emergencia médica en casa?
3. ¿Cómo monitorea actualmente el estado de salud y los signos vitales de su familiar o paciente?
4. ¿Qué signos vitales (presión, temperatura, pulso) considera más críticos de monitorear?
5. ¿Qué herramientas o equipos tecnológicos utiliza actualmente para el seguimiento de salud en casa?
6. ¿Estaría dispuesto a utilizar una plataforma web para recibir alertas en su celular si algo anda mal?
7.	¿Qué valor le da a tener un historial de salud completo para mostrarle al médico en las consultas?

Segmento objetivo 2: Adultos mayores (60+) con enfermedades crónicas: El objetivo es evaluar la aceptación de la tecnología y la percepción de seguridad que les brinda el dispositivo.

1.	¿Se siente seguro quedándose solo en casa durante el día?
2.	¿Le resulta difícil recordar tomarse la temperatura o medirse la presión regularmente?
3.  ¿Cómo monitorea actualmente el estado de salud y los signos vitales de su familiar o paciente?
4.  ¿Cómo se siente con la idea de usar un pequeño dispositivo que envíe sus datos de salud a sus hijos o médicos?
5.  ¿Qué es lo que más le asusta de tener una emergencia médica cuando no hay nadie cerca?
6.  ¿Qué herramientas o equipos tecnológicos utiliza actualmente para el seguimiento de salud en casa?
7.	Si tuviera un sistema que avisa automáticamente a su familia si se siente mal, ¿le daría más tranquilidad en su vida diaria?

### 5.3.2. Registro de Entrevistas
| Campo | Detalle                                                                                                                                                                                                                                                    |
| :--- |:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Entrevistada** | Briana Casarreto                                                                                                                                                                                                                                           |
| **Edad** | 25 años                                                                                                                                                                                                                                                    |
| **Distrito** | Santiago de Surco, Lima                                                                                                                                                                                                                                    |
| **Perfil y Experiencia** | Cuidadora con 2 años de experiencia en el sector de adultos mayores. Trabaja con pacientes que tienen limitaciones tecnológicas o de salud que les impiden comunicarse de forma autónoma.                                                                  |
| **Problemática Identificada** | Dependencia crítica de terceros. Ante la falta de herramientas digitales, Briana depende de llamadas de vecinos del condominio para enterarse de emergencias (caídas o fiebre), lo que genera una brecha de información peligrosa cuando no está presente. |
| **Dificultades Principales** | Riesgo de reacción tardía ante anomalías en presión arterial y pulso. La falta de un registro constante impide detectar tendencias de salud preventivas, actuando solo cuando la emergencia ya ocurrió.                                                    |
| **Necesidad Tecnológica** | Valida la necesidad de una plataforma de alertas y registro digital. Considera que un historial completo permitiría intervenciones médicas mucho más inmediatas y precisas.                                                                                |
| **Perfil Técnico** | Usuario de Android (Smartphone) y Windows (Laptop). Navegador principal: Google Chrome.                                                                                                                                                                    |
| **Evidencia visual** | <img src="assets/etrecista briana.jpg" /> / [Link al Video](https://drive.google.com/file/d/1LmHdxIzJqAQxy8f5lF-z4ZjDAaRHQd_p/view?usp=sharing)**                                                                                                          |
| **Pregunta 1: ¿Nivel de preocupación?** | Muy alto. Al no tener el familiar herramientas tecnológicas para comunicarse, la preocupación es constante cuando ella sale de casa.                                                                                                                       |
| **Pregunta 2: ¿Cómo se entera de emergencias?** | Por llamadas directas del paciente o, frecuentemente, a través de los vecinos del condominio si ocurre algo grave como una caída.                                                                                                                          |
| **Pregunta 3: ¿Signos más críticos?** | Presión arterial y pulso son su enfoque principal. También la temperatura si hay antecedentes recientes de fiebre.                                                                                                                                         |
| **Pregunta 4: ¿Usaría una plataforma de alertas?** | Sí, lo considera una excelente idea para tener un monitoreo exacto y recibir avisos cuando no está físicamente con el familiar.                                                                                                                            |
| **Pregunta 5: ¿Valor del historial médico?** | Muy valioso. Afirma que permitiría al doctor tener un detalle preciso para que la medicación sea inmediata y efectiva.                                                                                                                                     |

| Campo | Detalle                                                                                                                                                                                                                                  |
| :--- |:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Entrevistado** | Kevin Pacotaipe                                                                                                                                                                                                                          |
| **Edad** | 28 años                                                                                                                                                                                                                                  |
| **Distrito** | San Juan de Lurigancho, Lima                                                                                                                                                                                                             |
| **Perfil y Experiencia** | Técnico en soporte de sistemas. Responsable desde hace 3 años de la salud de su abuela (72 años) con hipertensión y diabetes. Trabaja fuera de casa, lo que genera una preocupación constante por no poder supervisarla presencialmente. |
| **Problemática Identificada** | "Ceguera de datos" durante la jornada laboral. Kevin depende exclusivamente de que su abuela lo llame por teléfono, lo cual es poco confiable si ella pierde el conocimiento o no puede manipular el celular en una crisis.              |
| **Dificultades Principales** | Monitoreo manual e irregular (solo 2-3 veces por semana). La falta de registros precisos de presión arterial y frecuencia cardíaca dificulta que el médico brinde diagnósticos exactos en las consultas.                                 |
| **Necesidad Tecnológica** | Valida totalmente una plataforma web con alertas automáticas. Busca "paz mental" mediante un sistema que le avise de anomalías sin depender de una acción manual de su abuela.                                                           |
| **Perfil Técnico** | Usuario avanzado (Soporte de sistemas). Maneja Android y Windows. Navegador principal: Google Chrome.                                                                                                                                    |
| **Evidencia visual** | <img src="assets/Entrevista 3.jpeg" />                                                                                                                                                                                                   |
| **Pregunta 1: ¿Nivel de preocupación?** | Constante, especialmente en horas de trabajo. A veces le cuesta concentrarse pensando si su abuela tomó sus medicinas o si se siente bien.                                                                                               |
| **Pregunta 2: ¿Cómo se entera de emergencias?** | Solo si ella lo llama. Reconoce que es un método arriesgado porque en una emergencia real ella podría no estar en condiciones de marcar.                                                                                                 |
| **Pregunta 3: ¿Cómo monitorea la salud?** | Manualmente durante sus visitas (2 o 3 veces por semana) usando un tensiómetro casero.                                                                                                                                                   |
| **Pregunta 4: ¿Signos más críticos?** | Presión arterial y frecuencia cardíaca por la hipertensión. También considera importante la temperatura como indicador preventivo.                                                                                                       |
| **Pregunta 5: ¿Equipos actuales?** | Tensiómetro digital básico y termómetro. No usan ninguna app o plataforma digital actualmente.                                                                                                                                           |
| **Pregunta 6: ¿Usaría una plataforma de alertas?** | Sí, sin dudarlo. Lo ve como una herramienta esencial para su tranquilidad mientras trabaja.                                                                                                                                              |
| **Pregunta 7: ¿Valor del historial médico?** | Muy alto. Menciona que la falta de datos precisos en las consultas actuales dificulta el trabajo del médico.                                                                                                                             |

| Campo | Detalle                                                                                                                                                                                                          |
| :--- |:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Entrevistada** | Nelsida Arnao                                                                                                                                                                                                    |
| **Edad** | 55 años                                                                                                                                                                                                          |
| **Distrito** | Surquillo, Lima                                                                                                                                                                                                  |
| **Perfil y Experiencia** | Ama de casa diagnosticada con diabetes tipo 2 e hipertensión hace 6 años. Pasa la mayor parte del día sola, lo que genera una percepción de inseguridad ante posibles crisis médicas como mareos o taquicardias. |
| **Problemática Identificada** | Incumplimiento del monitoreo: Debido a las tareas del hogar, olvida medirse la presión. Existe una barrera emocional: prefiere no "alarmar" a su hija, lo que retrasa la petición de ayuda en momentos críticos. |
| **Dificultades Principales** | Dificultad física para pedir ayuda (temblor en las manos durante crisis). No lleva un registro ordenado de signos vitales entre las consultas mensuales con su médico.                                           |
| **Necesidad Tecnológica** | Aceptación de dispositivos IoT pasivos. Valora la autonomía y la paz mental que brindaría un sistema que avise automáticamente a su familia si detecta anomalías.                                                |
| **Perfil Técnico** | Usuario de Android (Gama media). Uso frecuente de WhatsApp y YouTube. Navegador: Chrome (uso esporádico).                                                                                                        |
| **Evidencia visual** | <img src="assets/Entrevista4.jpeg" />                                                                                                                                                                            |
| **Pregunta 1: ¿Se siente segura sola?** | No siempre. Los mareos y taquicardias la hacen dudar si llamar a alguien, prefiriendo no alarmar a su hija pero reconociendo el riesgo.                                                                          |
| **Pregunta 2: ¿Olvida sus mediciones?** | Sí, frecuentemente olvida medirse la presión por estar ocupada con las tareas del hogar.                                                                                                                         |
| **Pregunta 3: ¿Cómo monitorea su salud?** | Usa un tensiómetro de forma irregular y asiste a controles mensuales, pero no tiene un registro ordenado de sus signos.                                                                                          |
| **Pregunta 4: ¿Usaría un dispositivo IoT?** | Sí, aunque inicialmente dudó por la privacidad, considera que la tranquilidad de sus hijos es más importante.                                                                                                    |
| **Pregunta 5: ¿Qué es lo que más le asusta?** | No poder pedir ayuda a tiempo. Ya vivió una experiencia donde no podía llamar por teléfono debido al temblor en sus manos.                                                                                       |
| **Pregunta 6: ¿Qué tecnología usa hoy?** | Solo equipos manuales (tensiómetro y termómetro). No utiliza apps de salud ni otros dispositivos inteligentes.                                                                                                   |
| **Pregunta 7: ¿Le daría tranquilidad un sistema automático?** | Definitivamente sí. Le daría confianza para estar sola y evitaría que su hija tenga que llamarla constantemente por preocupación.                                                                                |

| Campo                      | Detalle                                                                                                                                                                                                                                                         |  
| -------------------------- |-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
| Entrevistada               | Ximena Bardales                                                                                                                                                                                                                                                 |  
| Edad                       | 29 años                                                                                                                                                                                                                                                         |  
| Distrito                   | Lima (Contexto urbano)                                                                                                                                                                                                                                          |  
| Perfil y Experiencia       | Ximena representa al perfil de cuidador joven que equilibra estudios y trabajo. Es la responsable de la supervisión de su abuelo, pero sus responsabilidades externas limitan severamente el tiempo que puede dedicarle presencialmente.                        |  
| Problemática Identificada | Ansiedad por ausencia prolongada: El estado de "preocupación todo el tiempo" se debe a la imposibilidad física de estar en casa. Su método de comunicación (WhatsApp/Llamadas) depende enteramente de que el abuelo esté en condiciones de usar el dispositivo. |  
| Dificultades Principales   | Falta de instrumentación médica: No cuenta con equipos de medición en casa. Identifica el ritmo cardíaco como la métrica más crítica de la cual carece de datos en tiempo real.                                                                                 |  
| Necesidad Tecnológica      | Valida el uso de una plataforma web de monitoreo remoto como una herramienta de ayuda necesaria para mantener la vigilancia mientras se encuentra fuera del hogar.                                                                                              |  
| Importancia del Historial  | Reconoce que el registro de antecedentes es vital para la precisión del diagnóstico médico, alineándose con la propuesta de valor de VitalCare sobre la gestión de datos históricos.                                                                            |  
| Introducción               | Buenas tardes. Estoy realizando una entrevista para el curso de desarrollo open source, con la finalidad de medir el nivel de ansiedad que genera la falta de supervisión de un familiar.                                                                       |  
| Evidencia visual           | <img src="assets/entrevista2.jpeg" />                                                                                                                                                                                                                             |  
| Pregunta 1                 | Todo el tiempo, ya que estudio y trabajo, y eso no me permite estar muy pendiente de mi abuelo.                                                                                                                                                                 |  
| Pregunta 2                 | Él me lo hace saber por medio de WhatsApp o incluso puede llamarme.                                                                                                                                                                                             |  
| Pregunta 3                 | El corazón, ya que no tengo instrumentos en casa.                                                                                                                                                                                                               |  
| Pregunta 4                 | Sí, sería de mucha ayuda, ya que normalmente no estoy en casa y quisiera estar pendiente de mi abuelo.                                                                                                                                                          |  
| Pregunta 5                 | Es importante conocer los antecedentes de la persona para tener un diagnóstico más preciso.       
### 5.3.3. Evaluaciones según heurísticas
### 5.3.3. Evaluaciones según heurísticas

#### Anexo D. Formato para Evaluación de User Experience según Heurísticas

**UX Heuristics & Principles Evaluation**
**Usability – Inclusive Design – Information Architecture**

| Campo | Valor |
| :--- | :--- |
| **CARRERA** | Ingeniería de Software |
| **CURSO** | Desarrollo de Aplicaciones Open Source |
| **SECCIÓN** | 10177 |
| **PROFESORES** | Mori Paiva, Hugo Allan |
| **AUDITOR** | ByteCore — Bardales Tejada Luis Alexis, Caisahuana Osores Becker Junior, Huaman Gallardo Bruno Aldair, Rioja Nuñez Franco Diego, Rocca Mariaca Angel Mathias |
| **CLIENTE(S)** | Usuarios pertenecientes a los segmentos objetivo del producto VITAL CARE (adultos mayores y familiares/cuidadores) |

---

#### SITE o APP A EVALUAR:

**VITAL CARE** — Landing Page y Frontend Web Application

URL Landing Page: [https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/](https://1asi0729-2610-10177-bytecore-vitalcare.github.io/VitalCare-Landing-Page/)

---

#### TAREAS A EVALUAR:

El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas:

1. Navegar entre las secciones de la Landing Page mediante el menú superior.
2. Visualizar la propuesta de valor del producto en la sección Hero.
3. Conocer las funcionalidades de VITAL CARE en la sección de Beneficios/Features.
4. Conocer a los integrantes del equipo ByteCore en la sección Startup.
5. Visualizar los planes disponibles del producto.
6. Cambiar el idioma de la interfaz (Español / Inglés).
7. Registrar un nuevo usuario en el Frontend Web Application.
8. Iniciar sesión con credenciales válidas.
9. Navegar dentro del Dashboard principal de la aplicación.
10. Cerrar sesión desde el Dashboard.

No están incluidas en esta versión de la evaluación las siguientes tareas:

1. Visualizar el monitoreo de signos vitales en tiempo real desde el dispositivo IoT.
2. Recibir y gestionar alertas inteligentes ante variaciones críticas de signos vitales.
3. Agendar una cita con un profesional de la salud desde la aplicación.
4. Consultar el historial clínico digital del paciente.
5. Establecer comunicación directa entre el adulto mayor y su cuidador familiar.
6. Generar reportes médicos exportables en PDF.

---

#### ESCALA DE SEVERIDAD:

Los errores serán puntuados tomando en cuenta la siguiente escala de severidad:

| Nivel | Descripción |
| :---: | :--- |
| 1 | Problema superficial: puede ser fácilmente superado por el usuario o ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo. |
| 2 | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja resolverlo de cara al siguiente release. |
| 3 | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlos. Es importante que sean corregidos y se les debe asignar una prioridad alta. |
| 4 | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento. |

---

#### TABLA RESUMEN:

| # | Problema | Escala de severidad | Heurística/Principio violado |
| :---: | :--- | :---: | :--- |
| 1 | Las acciones del usuario (envío de formularios y navegación entre rutas) no muestran indicadores de carga | 2 | Usability: Visibilidad del estado del sistema |
| 2 | El formulario de contacto no muestra una confirmación clara al completar el envío del mensaje | 3 | Usability: Visibilidad del estado del sistema |
| 3 | No existe una manera evidente de regresar al estado anterior tras navegar entre secciones del Dashboard | 2 | Usability: Libertad y control del usuario |
| 4 | Los mensajes de error en los formularios de registro e inicio de sesión son genéricos y no orientan al usuario | 3 | Usability: Ayuda al usuario a reconocer, diagnosticar y recuperarse de errores |
| 5 | Algunas imágenes de la Landing Page no incluyen atributo `alt` descriptivo para lectores de pantalla | 3 | Inclusive Design: Proporciona experiencias comparables |
| 6 | El contraste de algunos textos sobre fondos claros es insuficiente para usuarios con baja visión | 2 | Inclusive Design: Proporciona experiencias comparables |
| 7 | No existe una sección de Ayuda o Preguntas Frecuentes accesible desde la Landing Page o la aplicación | 2 | Usability: Ayuda y documentación |
| 8 | El botón de Cerrar Sesión no es claramente identificable dentro del Dashboard principal | 2 | Usability: Libertad y control del usuario |
| 9 | La aplicación no cuenta con un buscador global que permita encontrar funcionalidades rápidamente | 1 | Information Architecture: Is it findable? |
| 10 | No queda totalmente claro qué planes y funcionalidades están disponibles para cada tipo de usuario | 2 | Information Architecture: Is it useful? |
| 11 | No se valida en tiempo real el formato del correo electrónico ni la fortaleza de la contraseña en el formulario de registro | 3 | Usability: Prevención de errores |
| 12 | La tipografía del cuerpo de texto en la Landing Page resulta pequeña para usuarios adultos mayores | 2 | Inclusive Design: Proporciona experiencias comparables |

---

#### DESCRIPCIÓN DE PROBLEMAS:

##### PROBLEMA #1: Falta de indicadores de carga durante acciones del usuario

**Severidad:** 2
**Heurística violada:** Usability — Visibilidad del estado del sistema

**Problema:**
Cuando el usuario envía el formulario de contacto en la Landing Page, o cuando inicia sesión y se realizan llamadas al Fake API desde el Frontend Web Application, no se muestra un indicador de carga (spinner, barra de progreso o skeleton loader). Esto puede generar incertidumbre en el usuario, quien no sabe si la aplicación está procesando su solicitud o si ocurrió un error.

**Recomendación:**
Implementar componentes de Angular Material como `MatProgressSpinner` o `MatProgressBar` que se muestren durante el tiempo en el que se ejecutan las peticiones HTTP. Adicionalmente, considerar el uso de Skeleton Loaders en los componentes de listado que consumen datos del backend.

---

##### PROBLEMA #2: Ausencia de confirmación al enviar el formulario de contacto

**Severidad:** 3
**Heurística violada:** Usability — Visibilidad del estado del sistema

**Problema:**
Al completar el formulario de contacto en la Landing Page y presionar el botón "Enviar", el sistema no muestra un mensaje de confirmación claro que indique al usuario que su mensaje ha sido recibido exitosamente. El usuario queda en duda sobre si la acción fue completada o si necesita repetirla.

**Recomendación:**
Mostrar un mensaje de confirmación visible (toast, snackbar o modal) tras el envío exitoso del formulario, con un texto claro como "Tu mensaje fue enviado exitosamente. Te responderemos en las próximas 24 horas." Adicionalmente, limpiar los campos del formulario y deshabilitar temporalmente el botón "Enviar" para prevenir envíos duplicados.

---

##### PROBLEMA #3: Imposibilidad de regresar al estado anterior tras navegar entre secciones del Dashboard

**Severidad:** 2
**Heurística violada:** Usability — Libertad y control del usuario

**Problema:**
Una vez que el usuario navega a una sección del Dashboard, no existe un botón explícito de "Atrás" dentro de la interfaz. Si bien el navegador permite usar el botón de retroceso, esto no resulta intuitivo para todos los usuarios, especialmente para adultos mayores con menor familiaridad con interfaces web.

**Recomendación:**
Incorporar un botón de navegación "Atrás" o un breadcrumb visible en la barra superior del Dashboard que permita al usuario regresar al estado anterior sin depender de los controles del navegador. Implementar la directiva `RouterLink` con `[routerLink]="['../']"` para facilitar la navegación contextual.

---

##### PROBLEMA #4: Mensajes de error genéricos en los formularios de autenticación

**Severidad:** 3
**Heurística violada:** Usability — Ayuda al usuario a reconocer, diagnosticar y recuperarse de errores

**Problema:**
Cuando el usuario ingresa credenciales incorrectas en el formulario de inicio de sesión, o cuando completa el formulario de registro con información inválida, los mensajes de error que se muestran son genéricos (por ejemplo: "Error al iniciar sesión" o "Datos inválidos") y no orientan al usuario sobre cuál campo específico presenta el problema ni qué acción debe tomar para corregirlo.

**Recomendación:**
Personalizar los mensajes de error para que indiquen claramente:
1. El campo específico que presenta el problema.
2. La razón del error.
3. La acción sugerida para corregirlo.

Por ejemplo, en lugar de "Error al iniciar sesión", mostrar "El correo electrónico ingresado no está registrado en VitalCare. ¿Deseas crear una cuenta?". Utilizar los validadores reactivos de Angular y los componentes `MatError` de Angular Material.

---

##### PROBLEMA #5: Imágenes sin atributo `alt` descriptivo

**Severidad:** 3
**Heurística violada:** Inclusive Design — Proporciona experiencias comparables

**Problema:**
Algunas imágenes utilizadas en la Landing Page (ilustraciones del hero, fotografías del equipo, íconos decorativos) no incluyen el atributo `alt` con una descripción significativa. Esto impide que los usuarios con discapacidad visual que utilizan lectores de pantalla puedan acceder al contenido visual.

**Recomendación:**
Revisar todas las etiquetas `<img>` del proyecto y asegurar que cada una incluya un atributo `alt` descriptivo. Para imágenes decorativas que no aportan información, utilizar `alt=""` (vacío) para que los lectores de pantalla las ignoren correctamente. Ejemplo:

```html
<img src="hero-vitalcare.png" alt="Adulto mayor utilizando el parche de monitoreo de VitalCare junto a un familiar">
```

---

##### PROBLEMA #6: Contraste insuficiente en textos sobre fondos claros

**Severidad:** 2
**Heurística violada:** Inclusive Design — Proporciona experiencias comparables

**Problema:**
Algunos textos secundarios de la Landing Page (subtítulos, descripciones de features, footer) utilizan colores grises claros sobre fondos blancos, lo que genera un contraste por debajo del mínimo recomendado por las pautas WCAG 2.1 nivel AA (ratio de contraste 4.5:1 para texto normal). Esto dificulta la lectura para usuarios con baja visión, particularmente adultos mayores que conforman uno de los segmentos objetivo.

**Recomendación:**
Auditar todos los pares color de texto / color de fondo utilizando herramientas como WebAIM Contrast Checker o las DevTools de Chrome. Ajustar los tonos de texto secundario a un gris más oscuro (por ejemplo, `#595959` en lugar de `#999999`) que cumpla con el ratio mínimo de 4.5:1.

---

##### PROBLEMA #7: Ausencia de sección de Ayuda o Preguntas Frecuentes

**Severidad:** 2
**Heurística violada:** Usability — Ayuda y documentación

**Problema:**
Ni la Landing Page ni el Frontend Web Application incluyen una sección de Ayuda, Preguntas Frecuentes (FAQ) o Centro de Soporte. Los usuarios que tengan dudas sobre el funcionamiento del producto, los planes disponibles o los pasos para registrarse no tienen un recurso donde consultarlas, lo que puede generar frustración y abandono.

**Recomendación:**
Incorporar una sección de Preguntas Frecuentes accesible desde el footer de la Landing Page y desde el menú principal del Dashboard. Agrupar las preguntas por categorías (Sobre el producto, Sobre los planes, Sobre la cuenta, Sobre el dispositivo). Considerar a futuro la integración de un chatbot o sistema de tickets de soporte.

---

##### PROBLEMA #8: Botón de Cerrar Sesión poco visible dentro del Dashboard

**Severidad:** 2
**Heurística violada:** Usability — Libertad y control del usuario

**Problema:**
El botón o enlace para cerrar sesión dentro del Dashboard se encuentra en una ubicación poco evidente para el usuario (por ejemplo, dentro de un menú desplegable del avatar), lo que dificulta su acceso. Para usuarios adultos mayores, encontrar esta opción puede resultar particularmente confuso, generando preocupación sobre cómo salir de la aplicación de forma segura.

**Recomendación:**
Reubicar el botón de "Cerrar Sesión" en una posición más visible y accesible, como la parte inferior del sidenav o en la barra superior junto al nombre del usuario, utilizando un ícono universalmente reconocible (`exit_to_app` de Material Icons) acompañado del texto descriptivo.

---

##### PROBLEMA #9: Ausencia de buscador global en la aplicación

**Severidad:** 1
**Heurística violada:** Information Architecture — Is it findable?

**Problema:**
El Frontend Web Application no incluye un buscador global que permita a los usuarios encontrar rápidamente funcionalidades, configuraciones o información dentro de la aplicación. Si bien el sidenav presenta las opciones principales, conforme el producto crezca en funcionalidades este podría volverse insuficiente.

**Recomendación:**
Implementar un componente de búsqueda global en la barra superior del Dashboard que permita encontrar funcionalidades por palabras clave. Considerar el uso del componente `MatAutocomplete` de Angular Material para sugerir resultados en tiempo real. Esta mejora se considera de baja prioridad para el TB1, dado que el alcance funcional actual es reducido.

---

##### PROBLEMA #10: Falta de claridad sobre planes y funcionalidades por tipo de usuario

**Severidad:** 2
**Heurística violada:** Information Architecture — Is it useful?

**Problema:**
La sección de Planes en la Landing Page muestra las opciones disponibles, pero no comunica con claridad qué funcionalidades específicas están incluidas en cada plan ni cuál es la diferencia entre el plan para adultos mayores y el plan para familiares/cuidadores. Esto puede generar dudas en el usuario al momento de decidir qué plan contratar.

**Recomendación:**
Rediseñar la sección de Planes utilizando una tabla comparativa que liste las funcionalidades disponibles fila por fila, con marcas de verificación (✓) o de exclusión (✗) según el plan. Adicionalmente, agregar tooltips o iconos de información (`info_outline`) que expliquen brevemente qué hace cada funcionalidad.

---

##### PROBLEMA #11: Validación reactiva insuficiente en el formulario de registro

**Severidad:** 3
**Heurística violada:** Usability — Prevención de errores

**Problema:**
En el formulario de registro del Frontend Web Application, la validación del correo electrónico y de la contraseña se realiza únicamente al momento de enviar el formulario, no durante el llenado. Esto significa que el usuario puede completar todos los campos solo para descubrir al final que el formato del correo es incorrecto o que la contraseña no cumple con los requisitos mínimos.

**Recomendación:**
Implementar validadores reactivos con `Validators.email`, `Validators.minLength(8)` y validadores personalizados para fortaleza de contraseña que muestren retroalimentación visual inmediata (con `MatError`) conforme el usuario va llenando los campos. Incluir un medidor visual de fortaleza de contraseña (débil / media / fuerte).

---

##### PROBLEMA #12: Tipografía pequeña para el segmento de adultos mayores

**Severidad:** 2
**Heurística violada:** Inclusive Design — Proporciona experiencias comparables

**Problema:**
El tamaño de la tipografía utilizada en el cuerpo de texto de la Landing Page (descripciones de funcionalidades, textos legales del footer, contenido de la sección Startup) es de aproximadamente 14-15px, lo cual resulta pequeño para uno de los principales segmentos objetivo del producto: los adultos mayores, quienes pueden presentar disminución natural de la visión.

**Recomendación:**
Aumentar el tamaño base de la tipografía del cuerpo de texto a al menos 16px (1rem) y los títulos secundarios a 18-20px. Considerar adicionalmente incorporar un control de accesibilidad en el menú superior que permita al usuario aumentar el tamaño de la fuente con un click, similar a lo que ofrecen muchos sitios gubernamentales orientados a adultos mayores.

---

## 5.4. Video About-the-Product

---

# Conclusiones

## Conclusiones y recomendaciones

## Video About-the-Team


