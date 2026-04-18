<div align="center">

<img src="assets/upc_logo.png" alt="UPC Logo" width="300"/>

# UNIVERSIDAD PERUANA DE CIENCIAS APLICADAS

### Carrera: Ingeniería de Software

### Periodo: 2026-10

### Nombre del curso: Desarrollo de Aplicaciones Open Source (1ASI0729)

### NRC: 10177

### Nombre del profesor: Mori Paiva, Hugo Allan

## Informe de Trabajo Final

## Nombre del startup: ByteCore

## Nombre del producto: VITAL CARE

### Relación de integrantes:

<div style="text-align: center;">

| Apellidos y Nombres | Código de Alumno |
|:-------------------:|:----------------:|
| Bardales Tejada, Luis Alexis |    U201819276    |
| Caisahuana Osores, Becker Junior |    U202419462    |
| Huaman Gallardo, Bruno Aldair |    U202117762    |
| Rioja Nuñez, Franco Diego |    U202221597    |
| Rocca Mariaca, Angel Mathias |    U20231e515    |

</div>

### Abril, 2026

---

</div>

# Registro de Versiones del Informe

| Versión | Fecha | Autor | Descripción de modificación |
|---------|-------|-------|-----------------------------|
| 1.0 | 04/04/2026 | Rioja Nuñez, Franco Diego | Creación del reporte en formato Markdown. |

---

# Project Report Collaboration Insights

| Enlace del repositorio del informe del proyecto |
|-------------------------------------------------|
| https://github.com/1ASI0729-2610-10177-ByteCore-VitalCare/VitalCare-Proyect-Report.git |

A continuación, se brindará un mayor detalle sobre las actividades realizadas en cada entrega, la participación de cada miembro de la startup y las evidencias correspondientes.

## Desarrollo del reporte

#### TB1:

Capítulo II: Requirements Elicitation & Analysis

2.1. Competidores

En el mercado de soluciones tecnológicas para la salud y el monitoreo remoto de pacientes, existen diversas plataformas que ofrecen servicios de supervisión de signos vitales. A continuación, se detallan los competidores clave identificados:

•	Fitbit (Google Health): Competidor indirecto. Es una de las plataformas de consumo más populares. Permite a los usuarios monitorear la frecuencia cardíaca, el sueño y la actividad física. Si bien está enfocada en el bienestar general, muchos cuidadores la utilizan para supervisar a adultos mayores, aunque carece de un sistema de alertas médicas críticas integrado para terceros.

•	KardiaMobile (AliveCor): Competidor directo en tecnología. Dispositivo IoT especializado en la detección de anomalías cardíacas con alertas.

•	CuidaCare: Competidor directo en segmento. Plataforma de gestión de cuidadores para adultos mayores, aunque con menor enfoque en la captura automática de datos IoT.

2.2. Análisis competitivo

| Característica       | VitalCare                                                                 | Fitbit                                                                | KardiaMobile                                                              | CuidaCare                                                               |
| --------------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| Perfil                | Plataforma web de monitoreo remoto con alertas IoT en tiempo real.        | Ecosistema de wearables para actividad, sueño y salud general.         | Dispositivo médico portátil de grado clínico para ECG instantáneo.        | App para gestión de tareas, medicación y comunicación entre cuidadores. |
| Ventaja Competitiva  | Automatización total mediante IoT Open Source y alertas críticas.         | Marca consolidada y ecosistema de hardware estético y funcional.       | Alta precisión y certificación médica de sus sensores de ECG.             | Enfoque en la organización humana y logística del cuidado.             |
| Mercado Objetivo      | Familiares (25-50 años) de adultos mayores en zonas urbanas.              | Personas activas y entusiastas del fitness y salud preventiva.         | Pacientes con arritmias o condiciones cardíacas específicas.              | Familias que dependen de cuidadores externos o enfermeros.             |
| Marketing             | Contenidos sobre salud digital y alianzas con comunidades.                 | Publicidad masiva, influencers y presencia en grandes retailers.       | Alianzas con cardiólogos y distribución en farmacias.                     | Boca a boca y presencia en agencias de enfermería.                      |
| Productos             | App Web + Integración con sensores ESP32/Arduino.                          | Wearables + Suscripción Premium a reportes.                            | Dispositivo de hardware + App de análisis médico.                          | Suscripción mensual a plataforma de gestión.                           |
| Precios               | Plan Básico gratis; Premium: $4.99/mes.                                  | Hardware desde $79 + Premium $9.99/mes.                               | Hardware único ($99) + Plan de reporte opcional.                         | Suscripción mensual según número de cuidadores.                          |
| Distribución          | Plataforma Web (SaaS) vía navegador.                                      | Tiendas físicas (iShop, Coolbox) y apps.                               | Farmacias, Amazon y sitio web oficial.                                    | App Store y Google Play.                                               |

| Análisis SWOT     | 
|                      | VitalCare                                      | Fitbit                                          | KardiaMobile                                      | CuidaCare                                            |
|----------------------|------------------------------------------------|-------------------------------------------------|---------------------------------------------------|------------------------------------------------------|
| **Fortalezas**       | Bajo costo (IoT Open Source) y alertas automáticas. | Respaldo de Google y diseño de producto impecable. | Validación clínica médica y portabilidad extrema. | Mejora la coordinación de múltiples cuidadores.      |
| **Debilidades**      | Dependencia crítica de la conexión a internet.     | Enfoque general; no para emergencias críticas.     | Solo monitorea el corazón; falta visión integral.  | Registro manual; propenso a errores u olvidos.       |
| **Oportunidades**    | Crecimiento de población adulta mayor en Perú.   | Expansión hacia seguros de salud integrados.       | Integración con sistemas hospitalarios públicos. | Digitalización de agencias de enfermería.           |
| **Amenazas**         | Competencia de hardware chino barato.           | Cambios en leyes globales de privacidad de datos. | Regulaciones sanitarias locales más estrictas.   | Apps de telemedicina con monitoreo gratuito.        |


2.3. Estrategias y tácticas frente a competidores.

•	Diferenciación mediante IoT real: A diferencia de las aplicaciones de registro manual, VitalCare se distinguirá por capturar datos de forma automática, lo que evitará errores humanos y permitirá respuestas rápidas a cualquier irregularidad. 

•	Transparencia de Código Abierto: Al tratarse de un proyecto de desarrollo abierto, se ayudará a aumentar la confianza en el manejo de información de salud, y se facilitará la conexión con diversos tipos de sensores económicos, disminuyendo la barrera de costos para las familias en Perú. 


•	Alertas de Prevención: Se planea usar la integración de información externa (como el clima) en el plan Premium para advertir sobre posibles riesgos de hipertensión o dificultades respiratorias antes de que sucedan.

2.3. Diseño de entrevista 

Segmento objetivo 1: Adultos entre 25 y 50 años que cuidan familiares: El objetivo es medir el nivel de ansiedad por la falta de supervisión y la disposición a pagar por un sistema de alertas automáticas.

1.	¿Qué tan seguido se preocupa por el estado de salud de su familiar cuando no está con él/ella?
2.	¿Cómo se entera actualmente si su familiar tiene una emergencia médica en casa?
3.	¿Qué signos vitales (presión, temperatura, pulso) considera más críticos de monitorear?
4.	¿Estaría dispuesto a utilizar una plataforma web para recibir alertas en su celular si algo anda mal?
5.	¿Qué valor le da a tener un historial de salud completo para mostrarle al médico en las consultas?

Segmento objetivo 2: Adultos mayores (60+) con enfermedades crónicas: El objetivo es evaluar la aceptación de la tecnología y la percepción de seguridad que les brinda el dispositivo.

1.	¿Se siente seguro quedándose solo en casa durante el día?
2.	¿Le resulta difícil recordar tomarse la temperatura o medirse la presión regularmente?
3.	¿Cómo se siente con la idea de usar un pequeño dispositivo que envíe sus datos de salud a sus hijos o médicos?
4.	¿Qué es lo que más le asusta de tener una emergencia médica cuando no hay nadie cerca?
5.	Si tuviera un sistema que avisa automáticamente a su familia si se siente mal, ¿le daría más tranquilidad en su vida diaria?


---

# Contenido

- [Registro de Versiones del Informe](#registro-de-versiones-del-informe)
- [Project Report Collaboration Insights](#project-report-collaboration-insights)
- [Student Outcome](report/01-student-outcome.md)
- [Capítulo I: Introducción](report/11-chapter-I-introduction.md)
- [Capítulo II: Requirements Elicitation & Analysis](report/21-chapter-II-requirements.md)
- [Capítulo III: Requirements Specification](report/31-chapter-III-specifications.md)
- [Capítulo IV: Product Design](report/41-chapter-IV-design.md)
- [Capítulo V: Product Implementation, Validation & Deployment](report/51-chapter-V-implementation.md)
- [Bibliografía](report/99-bibliography.md)
- [Anexos](report/99-bibliography.md#anexos)
