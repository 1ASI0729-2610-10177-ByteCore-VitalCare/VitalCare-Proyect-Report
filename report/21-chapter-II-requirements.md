# Capítulo II: Requirements Elicitation & Analysis

Capítulo II: Requirements Elicitation & Analysis

2.1. Competidores

En el mercado de soluciones tecnológicas para la salud y el monitoreo remoto de pacientes, existen diversas plataformas que ofrecen servicios de supervisión de signos vitales. A continuación, se detallan los competidores clave identificados:

•	Fitbit (Google Health): Competidor indirecto. Es una de las plataformas de consumo más populares. Permite a los usuarios monitorear la frecuencia cardíaca, el sueño y la actividad física. Si bien está enfocada en el bienestar general, muchos cuidadores la utilizan para supervisar a adultos mayores, aunque carece de un sistema de alertas médicas críticas integrado para terceros.

•	KardiaMobile (AliveCor): Competidor directo en tecnología. Dispositivo IoT especializado en la detección de anomalías cardíacas con alertas.

•	CuidaCare: Competidor directo en segmento. Plataforma de gestión de cuidadores para adultos mayores, aunque con menor enfoque en la captura automática de datos IoT.

2.1.1 Análisis competitivo

<table>
  <tr>
    <th colspan="6">Competitive Analysis Landscape - Project: VITAL CARE</th>
  </tr>
  <tr>
    <td colspan="1">¿Por qué llevar a cabo el análisis?</td>
    <td colspan="5">El análisis competitivo es fundamental para identificar los puntos fuertes y débiles de VitalCare frente a gigantes del mercado de salud digital y wearables. Esto nos permite posicionar nuestra ventaja en la automatización IoT de bajo costo y el enfoque específico en cuidadores de adultos mayores en entornos urbanos, diferenciándonos de soluciones fitness o clínicas de alto costo.</td>
  </tr>
  <tr>
    <td colspan="2"></td>
    <td><b>VitalCare</b></td>
    <td><b>Fitbit (Google)</b></td>
    <td><b>KardiaMobile</b></td>
    <td><b>CuidaCare</b></td>
  </tr>
  <tr>
    <td colspan="2">Logo</td>
    <td><img src="assets/logo VitalCare.png" alt="VitalCare"/></td>
    <td><img src="assets/Google Fit.png" alt="Fitbit"/></td>
    <td><img src="assets/CardiaMobile.png" alt="KardiaMobile"/></td>
    <td><img src="assets/CuidaCare.png" alt="CuidaCare"/></td>
  </tr>
  <tr>
    <td rowspan="2">Perfil</td>
    <td>Overview</td>
    <td>Plataforma web de monitoreo remoto que utiliza dispositivos IoT (ESP32/Arduino) para obtener signos vitales en tiempo real, detectando anomalías y generando alertas automáticas para familiares en zonas urbanas.</td>
    <td>Ecosistema líder de wearables (pulseras y relojes) enfocado en el seguimiento de actividad física, calidad del sueño y métricas de salud general a través de hardware propietario estético.</td>
    <td>Dispositivo médico portátil con certificación clínica especializado en realizar electrocardiogramas (ECG) instantáneos para detectar arritmias desde un smartphone.</td>
    <td>Aplicación móvil diseñada para la gestión logística del cuidado, permitiendo organizar tareas, recordatorios de medicación y comunicación entre múltiples cuidadores.</td>
  </tr>
  <tr>
    <td>Ventaja competitiva ¿Qué valor ofrece a los clientes?</td>
    <td>Automatización total mediante hardware Open Source de bajo costo y alertas críticas preventivas, permitiendo una supervisión constante sin depender del registro manual del paciente.</td>
    <td>Marca global consolidada con un ecosistema de hardware muy estético, funcional y una comunidad de usuarios masiva respaldada por la infraestructura de Google.</td>
    <td>Alta precisión y validación de grado médico (FDA) en sus sensores, brindando confianza absoluta en el diagnóstico de condiciones cardíacas específicas.</td>
    <td>Optimización de la organización humana y logística, reduciendo el error en la administración de medicinas y mejorando la comunicación en familias con enfermeros externos.</td>
  </tr>
  <tr>
    <td rowspan="2">Perfil de Marketing</td>
    <td>Mercado Objetivo</td>
    <td>Familiares (25-50 años) que cuidan adultos mayores en zonas urbanas de Perú, con preocupación por emergencias médicas y necesidad de tranquilidad remota.</td>
    <td>Personas jóvenes y adultas activas, entusiastas del fitness y usuarios que buscan prevención de salud general a través de un estilo de vida saludable.</td>
    <td>Pacientes con antecedentes cardíacos, arritmias o condiciones específicas que requieren monitoreo clínico puntual pero frecuente.</td>
    <td>Familias que dependen de cuidadores externos, agencias de enfermería o múltiples familiares rotativos para la atención de un paciente.</td>
  </tr>
  <tr>
    <td>Estrategias de Marketing</td>
    <td>Marketing de contenidos sobre salud digital y alianzas estratégicas con comunidades de cuidado al adulto mayor y tecnología abierta.</td>
    <td>Publicidad masiva en medios digitales, uso de influencers de bienestar y presencia física en los principales retailers tecnológicos (iShop, Coolbox).</td>
    <td>Alianzas directas con cardiólogos, recomendación médica profesional y distribución especializada en farmacias y Amazon.</td>
    <td>Estrategia de boca a boca y presencia directa en agencias de enfermería privada y grupos de apoyo para cuidadores.</td>
  </tr>
  <tr>
    <td rowspan="3">Perfil de Producto</td>
    <td>Productos y Servicios</td>
    <td>Aplicación Web interactiva integrada con sensores IoT (ESP32), dashboard de signos vitales, alertas automáticas y reportes históricos.</td>
    <td>Variedad de dispositivos Wearables + App móvil + Suscripción Premium para análisis profundo de tendencias de salud y sueño.</td>
    <td>Hardware de bolsillo para ECG + Aplicación de análisis médico y posibilidad de compartir reportes directamente con el especialista.</td>
    <td>Suscripción a plataforma móvil de gestión de tareas, calendario de medicación y chat de coordinación para el equipo de cuidado.</td>
  </tr>
  <tr>
    <td>Precios y Costos</td>
    <td>Plan Básico: Gratis (1 paciente, 3 días de historial). Plan Premium: $4.99/mes (Múltiples pacientes, alertas avanzadas e historial completo).</td>
    <td>Costo de hardware inicial (desde $79) + Suscripción Premium opcional de $9.99/mes para funciones avanzadas.</td>
    <td>Pago único por el hardware ($99 aprox.) + Plan de reporte médico opcional bajo demanda.</td>
    <td>Modelo de suscripción mensual basado en el número de cuidadores o perfiles de pacientes registrados.</td>
  </tr>
  <tr>
    <td>Canales de distribución (Web y/o Móvil)</td>
    <td>Plataforma Web (SaaS) accesible desde cualquier navegador; notificaciones vía Web, Email o Push.</td>
    <td>Tiendas físicas minoristas, plataformas de e-commerce y App Store / Google Play.</td>
    <td>Farmacias especializadas, Amazon y sitio web oficial del fabricante.</td>
    <td>Exclusivo a través de tiendas de aplicaciones móviles (App Store y Google Play).</td>
  </tr>
  <tr>
    <td rowspan="4">Análisis SWOT</td>
    <td>Fortalezas</td>
    <td>Costo de implementación muy bajo debido al uso de tecnología Open Source y capacidad de respuesta inmediata ante crisis mediante alertas.</td>
    <td>Diseño de producto superior, integración perfecta con servicios de Google y gran autonomía de batería en sus dispositivos.</td>
    <td>Validación médica internacional, portabilidad extrema y enfoque en una necesidad crítica (salud cardíaca) con alta precisión.</td>
    <td>Facilita la gestión humana de casos complejos donde intervienen muchos cuidadores, evitando la duplicidad de tareas.</td>
  </tr>
  <tr>
    <td>Debilidades</td>
    <td>Dependencia absoluta de la conectividad a internet en el hogar del paciente y hardware que requiere mantenimiento básico del usuario.</td>
    <td>Su enfoque es demasiado general; no está diseñado específicamente para reaccionar ante emergencias médicas críticas en tiempo real.</td>
    <td>Monitoreo limitado exclusivamente al corazón; no ofrece una visión integral de otros signos vitales como temperatura o saturación.</td>
    <td>Depende totalmente del ingreso manual de datos por parte del cuidador, lo que lo hace propenso a errores humanos u olvidos.</td>
  </tr>
  <tr>
    <td>Oportunidades</td>
    <td>Crecimiento acelerado de la población adulta mayor en Perú y la falta de soluciones locales accesibles de monitoreo IoT.</td>
    <td>Potencial de integración con seguros de salud privados para ofrecer descuentos basados en métricas de vida saludable.</td>
    <td>Posibilidad de integrarse con sistemas de telemedicina de hospitales públicos para monitoreo remoto de pacientes post-operados.</td>
    <td>Digitalización de las agencias de enfermería y servicios de "Home Care" que aún utilizan registros en papel.</td>
  </tr>
  <tr>
    <td>Amenazas</td>
    <td>Competencia de dispositivos genéricos de bajo costo provenientes del mercado chino con apps integradas.</td>
    <td>Regulaciones de privacidad de datos cada vez más estrictas que podrían limitar el uso de información sensible de salud.</td>
    <td>Nuevas regulaciones sanitarias locales (DIGEMID) que podrían exigir certificaciones costosas para dispositivos médicos.</td>
    <td>Aparición de apps de telemedicina que incluyan módulos de gestión de tareas de forma gratuita.</td>
  </tr>
</table>

2.1.2. Estrategias y tácticas frente a competidores.

•	Diferenciación mediante IoT real: A diferencia de las aplicaciones de registro manual, VitalCare se distinguirá por capturar datos de forma automática, lo que evitará errores humanos y permitirá respuestas rápidas a cualquier irregularidad.

•	Transparencia de Código Abierto: Al tratarse de un proyecto de desarrollo abierto, se ayudará a aumentar la confianza en el manejo de información de salud, y se facilitará la conexión con diversos tipos de sensores económicos, disminuyendo la barrera de costos para las familias en Perú.

2.2. Entrevistas.

Segmento objetivo 1: Adultos entre 25 y 50 años que cuidan familiares: El objetivo es medir el nivel de ansiedad por la falta de supervisión y la disposición a pagar por un sistema de alertas automáticas.

•	Alertas de Prevención: Se planea usar la integración de información externa (como el clima) en el plan Premium para advertir sobre posibles riesgos de hipertensión o dificultades respiratorias antes de que sucedan.

2.2.1. Diseño de entrevista

Estructura de Encuesta: VITAL CARE

Sección 0: Datos Generales (Para ambos segmentos)

Nombre completo: __________________________________

Edad: __________ años

Ocupación actual: __________________________________

Lugar de residencia (Distrito):__________________________________

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

2.2.2. Registro de entrevistas.


---

## 2.3. Needfinding

### 2.3.1. User Personas

### 2.3.2. User Task Matrix

### 2.3.3. User Journey Mapping

### 2.3.4. Empathy Mapping

---

## 2.4. Big Picture EventStorming

## 2.5. Ubiquitous Language
