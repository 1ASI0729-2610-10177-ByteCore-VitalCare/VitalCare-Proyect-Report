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


---

## 5.2. Landing Page, Services & Applications Implementation

### 5.2.1. Sprint 1

#### 5.2.1.1. Sprint Planning 1

#### 5.2.1.2. Aspect Leaders and Collaborators

#### 5.2.1.3. Sprint Backlog 1

#### 5.2.1.4. Development Evidence for Sprint Review

#### 5.2.1.5. Execution Evidence for Sprint Review

#### 5.2.1.6. Services Documentation Evidence for Sprint Review

#### 5.2.1.7. Software Deployment Evidence for Sprint Review

#### 5.2.1.8. Team Collaboration Insights during Sprint

---

## 5.3. Validation Interviews

### 5.3.1. Diseño de Entrevistas

### 5.3.2. Registro de Entrevistas

### 5.3.3. Evaluaciones según heurísticas

---

## 5.4. Video About-the-Product

---

# Conclusiones

## Conclusiones y recomendaciones

## Video About-the-Team
