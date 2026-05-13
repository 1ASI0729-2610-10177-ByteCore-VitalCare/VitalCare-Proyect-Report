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

| Sprint #                           | Sprint 2                                                                                                                                                                                                                                                                                                |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Sprint Planning Background**     |                                                                                                                                                                                                                                                                                                         |
| Date                               | 2026-05-10                                                                                                                                                                                                                                                                                              |
| Time                               | 04:30 PM                                                                                                                                                                                                                                                                                                |
| Location                           | Reunión virtual vía Google Meet                                                                                                                                                                                                                                                                         |
| Prepared By                        | Rioja Nuñez, Franco Diego                                                                                                                                                                                                                                                                               |
| Attendees                          | Bardales Tejada, Luis Alexis / Caisahuana Osores, Becker Junior / Huaman Gallardo, Bruno Aldair / Rioja Nuñez, Franco Diego / Rocca Mariaca, Angel Mathias                                                                                                                                              |
| Sprint 2 – 1 Review Summary        | Sprint 1 was very well coordinated; however, we didn't meet the requirements, resulting in a slight decrease in content quality. Team members are aware of these errors thanks to feedback provided by the Product Owner.                                                                               |
| Sprint 2 – 1 Retrospective Summary | The team acknowledges that the previous sprint's development didn't fully align with the requested requirements. Fortunately, the Product Owner provided significant support through consistent feedback, enabling us to identify errors and make the necessary corrections to improve product quality. |
| **Sprint Goal & User Stories**     |                                                                                                                                                                                                                                                                                                         |
| Sprint 1 Goal                      | Our focus is on strengthening VitalCare's digital presence through the launch of our web application. We believe this will effectively communicate our value proposition to families dealing with challenges in monitoring patients who require constant care.                                          |
| Sprint 1 Velocity                  | 78                                                                                                                                                                                                                                                                                                      |
| Sum of Story Points                | 24                                                                                                                                                                                                                                                                                                      |

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

En esta sección se evidencia la colaboración del equipo durante el Sprint 2 en el desarrollo de la primera versión del frontend de Vital Care.

**Repositorio de Frontend:** VitalCare-Frontend


---

## 5.3. Validation Interviews

### 5.3.1. Diseño de Entrevistas

### 5.3.3. Evaluaciones según heurísticas. 

## 5.4. Video About-the-Product

---

# Conclusiones

## Conclusiones y recomendaciones

## Video About-the-Team


