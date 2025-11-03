# Especificación de Requisitos de Software (SRS)
### Proyecto: [Nombre del Proyecto]
*Versión [1.0]*

<br>

<img width="445" height="127" alt="image" src="https://github.com/user-attachments/assets/a2cb6e38-e0cb-4149-b56f-a295d28b4a78" />

*[Mes de Año]*

<br>

> **Nota Aclaratoria:** <br>
> Este documento fue elaborado con fines académicos como parte de una práctica formativa bajo el estándar IEEE 830-1998.
> Todos los datos, nombres de entidades, diagramas y estructuras de base de datos son simulados y no corresponden a información real.
> Este documento tiene propósitos educativos y está diseñado para enseñar la correcta especificación de requisitos de software.

<br>

> **Instrucciones para el Estudiante:** <br>
> - Elimine todos los comentarios HTML `<!-- ... -->` en la versión final
> - Reemplace todo el texto entre `[corchetes]` con información real de su proyecto
> - Utilice las tablas y formatos sugeridos como guía
> - Revise el checklist de calidad antes de entregar
> - Mantenga la numeración y estructura del estándar IEEE 830

<br>

**Control de Versiones:**

| Versión | Fecha | Autor | Descripción de Cambios |
|---------|-------|-------|------------------------|
| 1.0 | [DD/MM/AAAA] | [Nombre] | Versión inicial del documento |
| | | | |

<br>

---

## CONTENIDO

- [1 INTRODUCCIÓN](#1-introducción)
  - [1.1 Propósito](#11-propósito)
  - [1.2 Alcance](#12-alcance)
  - [1.3 Personal involucrado](#13-personal-involucrado)
  - [1.4 Definiciones, acrónimos y abreviaturas](#14-definiciones-acrónimos-y-abreviaturas)
  - [1.5 Referencias](#15-referencias)
  - [1.6 Resumen](#16-resumen)
- [2 DESCRIPCIÓN GENERAL](#2-descripción-general)
  - [2.1 Perspectiva del producto](#21-perspectiva-del-producto)
  - [2.2 Funciones del producto](#22-funciones-del-producto)
  - [2.3 Características de los usuarios](#23-características-de-los-usuarios)
  - [2.4 Restricciones](#24-restricciones)
  - [2.5 Suposiciones y dependencias](#25-suposiciones-y-dependencias)
  - [2.6 Requisitos futuros](#26-requisitos-futuros)
- [3 REQUISITOS ESPECÍFICOS](#3-requisitos-específicos)
  - [3.1 Requisitos funcionales](#31-requisitos-funcionales)
  - [3.2 Requisitos de interfaz externa](#32-requisitos-de-interfaz-externa)
    - [3.2.1 Interfaz de usuario](#321-interfaz-de-usuario)
    - [3.2.2 Interfaz de hardware](#322-interfaz-de-hardware)
    - [3.2.3 Interfaz de software](#323-interfaz-de-software)
    - [3.2.4 Interfaz de comunicación](#324-interfaz-de-comunicación)
  - [3.3 Requisitos no funcionales](#33-requisitos-no-funcionales)
    - [3.3.1 Rendimiento](#331-rendimiento)
    - [3.3.2 Fiabilidad](#332-fiabilidad)
    - [3.3.3 Disponibilidad](#333-disponibilidad)
    - [3.3.4 Seguridad](#334-seguridad)
    - [3.3.5 Mantenibilidad](#335-mantenibilidad)
    - [3.3.6 Portabilidad](#336-portabilidad)
  - [3.4 Requisitos de diseño](#34-requisitos-de-diseño)
  - [3.5 Requisitos de calidad](#35-requisitos-de-calidad)
  - [3.6 Restricciones del sistema](#36-restricciones-del-sistema)
  - [3.7 Atributos del sistema](#37-atributos-del-sistema)
- [4 APÉNDICES](#4-apéndices)
  - [4.1 Modelos de casos de uso](#41-modelos-de-casos-de-uso)
  - [4.2 Glosario](#42-glosario)
  - [4.3 Diagramas del sistema](#43-diagramas-del-sistema)
  - [4.4 Matriz de trazabilidad](#44-matriz-de-trazabilidad)
  - [4.5 Criterios de evaluación](#45-criterios-de-evaluación)

<br>

---

## 1 INTRODUCCIÓN

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 1: INTRODUCCIÓN
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO DE ESTA SECCIÓN:
Proporcionar una visión general del documento de especificación de requisitos.
Esta sección debe ser comprensible para TODOS los lectores, incluyendo aquellos
sin conocimientos técnicos profundos (stakeholders, gerentes, clientes).

IMPORTANCIA ACADÉMICA:
La introducción establece el contexto del proyecto y facilita la comprensión
del documento. Una buena introducción permite que diferentes stakeholders 
comprendan rápidamente el propósito y alcance del sistema sin necesidad de 
leer todo el documento.

AUDIENCIA:
- Equipo de desarrollo
- Analistas de negocio
- Gerentes de proyecto
- Clientes/Stakeholders
- Equipo de QA y testing
- Futuros mantenedores del sistema
-->

### 1.1 Propósito

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Explicar claramente POR QUÉ existe este documento y QUIÉN lo utilizará.

QUÉ DEBE INCLUIR (2-4 párrafos):
✓ Objetivo principal del documento SRS
✓ Público objetivo específico (desarrolladores, testers, cliente, etc.)
✓ Cómo se utilizará el documento en el ciclo de vida del proyecto
✓ Alcance de versión o fase del proyecto (si aplica)

PREGUNTAS GUÍA:
1. ¿Para qué se crea este documento?
2. ¿Quiénes lo van a leer y usar?
3. ¿Qué decisiones se tomarán basándose en este documento?
4. ¿Este documento cubre todo el sistema o solo una versión/módulo?

ERRORES COMUNES A EVITAR:
✗ Ser demasiado vago: "Este documento describe un sistema"
✗ Confundir propósito del documento con propósito del sistema
✗ No especificar la audiencia
✗ Ser excesivamente técnico en esta sección

EJEMPLO ACADÉMICO:
"Este documento de Especificación de Requisitos de Software (SRS) describe los 
requisitos funcionales y no funcionales para el Sistema de Gestión Bibliotecaria 
'BiblioTech', versión 1.0. El propósito de este documento es establecer una base 
común de entendimiento entre el cliente (Biblioteca Municipal Central) y el equipo 
de desarrollo sobre lo que el sistema debe hacer y cómo debe comportarse.

Este documento será utilizado por:
- El equipo de desarrollo como guía para la implementación del sistema
- Los analistas de QA para diseñar casos de prueba
- El cliente para validar que sus necesidades están correctamente reflejadas
- Los gerentes de proyecto para planificar recursos y cronogramas

Las especificaciones aquí contenidas servirán como base contractual para la 
aceptación del sistema y como referencia durante todo el ciclo de vida del 
desarrollo."
-->

[Escriba aquí el propósito de este documento. Use los párrafos necesarios para explicar claramente por qué existe este SRS y quiénes lo utilizarán.]

<br>

### 1.2 Alcance

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Definir claramente QUÉ está incluido y QUÉ NO está incluido en este sistema.

QUÉ DEBE INCLUIR:
✓ Nombre oficial del sistema/software
✓ Descripción breve de lo que hace el sistema (2-3 párrafos)
✓ Beneficios principales que aportará
✓ Objetivos específicos y medibles
✓ Límites del sistema (qué NO incluye)
✓ Relación con otros sistemas (si aplica)

ESTRUCTURA SUGERIDA:

**Nombre del Sistema:**
[Nombre oficial completo]

**Descripción:**
[Explicar en 2-3 párrafos qué hace el sistema, cuál es su dominio de aplicación,
y qué problema resuelve]

**Beneficios Principales:**
- [Beneficio 1: ahorro de tiempo, reducción de errores, etc.]
- [Beneficio 2]
- [Beneficio 3]

**Objetivos del Sistema:**
1. [Objetivo medible 1: Ej. "Reducir el tiempo de préstamo de libros de 5 a 2 minutos"]
2. [Objetivo medible 2]
3. [Objetivo medible 3]

**Límites del Sistema (Fuera de Alcance):**
- [Lo que NO hará el sistema: Ej. "El sistema NO manejará la contabilidad interna de la biblioteca"]
- [Funcionalidad excluida explícitamente]

EJEMPLO ACADÉMICO:

**Nombre del Sistema:** Sistema de Gestión Bibliotecaria BiblioTech

**Descripción:**
BiblioTech es un sistema integral de gestión bibliotecaria diseñado para automatizar 
las operaciones diarias de bibliotecas públicas de tamaño mediano (10,000 a 50,000 
volúmenes). El sistema gestiona el catálogo de materiales, préstamos, devoluciones, 
reservas, y el registro de usuarios.

El sistema reemplazará el actual proceso manual de registro en tarjetas físicas y 
planillas Excel, proporcionando una plataforma centralizada, confiable y de fácil 
acceso para bibliotecarios y usuarios. BiblioTech también incluirá un módulo de 
consulta en línea para que los usuarios puedan buscar materiales y verificar 
disponibilidad desde sus hogares.

**Beneficios Principales:**
- Reducción del tiempo promedio de atención por usuario de 5 a 2 minutos
- Eliminación del 100% de los registros en papel
- Disponibilidad de información en tiempo real sobre el inventario
- Reducción de pérdidas de material mediante sistema automatizado de seguimiento
- Acceso remoto al catálogo 24/7 para los usuarios

**Objetivos del Sistema:**
1. Digitalizar el 100% del catálogo existente en los primeros 3 meses
2. Reducir en un 60% el tiempo de procesamiento de préstamos y devoluciones
3. Implementar sistema de notificaciones automáticas para devoluciones vencidas
4. Proveer reportes estadísticos mensuales sobre uso de la biblioteca
5. Garantizar disponibilidad del sistema del 99.5% durante horario de operación

**Límites del Sistema (Fuera de Alcance):**
- Gestión contable y presupuestaria de la biblioteca
- Sistema de punto de venta para librería anexa
- Gestión de recursos humanos y nómina del personal
- Sistema de seguridad física del edificio (cámaras, alarmas)
- Plataforma de e-books o biblioteca digital de contenidos
-->

[Complete esta sección siguiendo la estructura sugerida arriba]

<br>

### 1.3 Personal involucrado

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Identificar a todas las personas clave que participan en la definición, desarrollo,
y validación del sistema.

IMPORTANCIA:
Esta sección es crucial para:
- Establecer responsabilidades claras
- Facilitar la comunicación entre stakeholders
- Documentar la cadena de toma de decisiones
- Permitir contacto directo cuando surjan dudas

TABLA REQUERIDA:
Complete la siguiente tabla para cada persona involucrada en el proyecto.
Incluya mínimo: Cliente/Patrocinador, Jefe de Proyecto, Analista Principal,
y Líder de Desarrollo.
-->

| Nombre | Rol | Responsabilidades | Información de Contacto |
|--------|-----|-------------------|-------------------------|
| [Nombre completo] | Cliente/Patrocinador del Proyecto | - Aprobar requisitos<br>- Proporcionar retroalimentación<br>- Validar entregas<br>- Decisiones finales sobre alcance | Email: [correo]<br>Tel: [teléfono]<br>Organización: [nombre] |
| [Nombre completo] | Gerente/Jefe de Proyecto | - Coordinar equipo de desarrollo<br>- Gestionar recursos y cronograma<br>- Punto de contacto principal con cliente<br>- Resolución de conflictos | Email: [correo]<br>Tel: [teléfono] |
| [Nombre completo] | Analista de Requisitos | - Elicitación de requisitos<br>- Documentación de SRS<br>- Validación con stakeholders<br>- Gestión de cambios en requisitos | Email: [correo]<br>Tel: [teléfono] |
| [Nombre completo] | Arquitecto de Software / Líder Técnico | - Diseño de arquitectura del sistema<br>- Decisiones técnicas<br>- Revisión de código<br>- Establecer estándares de desarrollo | Email: [correo]<br>Tel: [teléfono] |
| [Nombre completo] | Líder de QA/Testing | - Diseño de estrategia de pruebas<br>- Validación de requisitos<br>- Asegurar calidad del producto<br>- Reportes de defectos | Email: [correo]<br>Tel: [teléfono] |

<!-- 
NOTA PARA PROYECTOS ACADÉMICOS:
En contextos académicos, pueden incluir roles como:
- Docente/Asesor del proyecto
- Estudiantes por rol (analista, desarrollador, tester)
- "Cliente simulado" o stakeholder de práctica
-->

<br>

### 1.4 Definiciones, acrónimos y abreviaturas

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Proporcionar un glosario de términos técnicos, acrónimos y abreviaturas utilizados
en el documento para garantizar comprensión común.

IMPORTANCIA:
Evita ambigüedades y malentendidos. Un mismo término puede significar cosas diferentes
en distintos contextos (ej: "usuario" puede ser usuario final o usuario del sistema).

ORGANIZACIÓN:
Liste los términos en orden alfabético para facilitar la consulta.

TIPOS DE ENTRADAS:
1. Términos del dominio del negocio
2. Términos técnicos de software
3. Acrónimos del proyecto
4. Abreviaturas utilizadas en el documento

FORMATO SUGERIDO:
-->

| Término | Definición |
|---------|------------|
| **API** | Application Programming Interface (Interfaz de Programación de Aplicaciones). Conjunto de definiciones y protocolos para integrar y comunicar aplicaciones de software. |
| **CRUD** | Create, Read, Update, Delete. Operaciones básicas de gestión de datos en una base de datos. |
| **Framework** | Estructura conceptual y tecnológica de soporte definida, normalmente con artefactos o módulos de software concretos, que puede servir de base para la organización y desarrollo de software. |
| **IEEE 830** | Estándar del Instituto de Ingenieros Eléctricos y Electrónicos para especificaciones de requisitos de software. |
| **RF** | Requisito Funcional. Especifica una función que debe realizar el sistema. |
| **RNF** | Requisito No Funcional. Especifica criterios de calidad, restricciones o atributos del sistema. |
| **SRS** | Software Requirements Specification (Especificación de Requisitos de Software). |
| **Stakeholder** | Cualquier persona, grupo u organización que puede afectar o ser afectado por el proyecto. |
| **UI** | User Interface (Interfaz de Usuario). Medio con que el usuario puede comunicarse con el sistema. |
| **UX** | User Experience (Experiencia de Usuario). Percepción y respuesta del usuario resultante del uso o anticipación del uso de un producto. |

<!-- 
INSTRUCCIONES:
1. Agregue TODOS los términos técnicos o del dominio que use en el documento
2. Agregue los acrónimos de su organización o proyecto específico
3. Defina términos ambiguos de manera precisa para su contexto
4. Si usa términos en inglés, incluya la traducción al español

EJEMPLO DE TÉRMINOS ESPECÍFICOS DE DOMINIO (Biblioteca):

| Término | Definición |
|---------|------------|
| **Ejemplar** | Copia física específica de un material bibliográfico. Un libro puede tener múltiples ejemplares. |
| **Material bibliográfico** | Cualquier recurso disponible en la biblioteca: libros, revistas, DVDs, etc. |
| **Préstamo a domicilio** | Tipo de préstamo que permite al usuario llevar material fuera de la biblioteca por un período determinado. |
| **Préstamo en sala** | Tipo de préstamo que solo permite consultar el material dentro de las instalaciones de la biblioteca. |
| **Usuario activo** | Usuario registrado que ha realizado al menos un préstamo en los últimos 12 meses. |
-->

[Complete la tabla con los términos específicos de su proyecto]

<br>

### 1.5 Referencias

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Listar todos los documentos, estándares, normas y recursos externos referenciados
en este SRS o que proporcionan contexto adicional.

IMPORTANCIA:
Permite a los lectores:
- Profundizar en temas específicos
- Validar el cumplimiento de estándares
- Acceder a documentación complementaria
- Verificar la trazabilidad con otros documentos del proyecto

TIPOS DE REFERENCIAS COMUNES:
1. Estándares y normas (IEEE, ISO, etc.)
2. Documentos del proyecto (plan de proyecto, visión, arquitectura)
3. Documentación técnica de frameworks o tecnologías
4. Bibliografía de referencia
5. Sitios web y recursos en línea

FORMATO SUGERIDO (estilo académico):
-->

**Estándares y Normas:**

1. IEEE Computer Society. (1998). *IEEE Recommended Practice for Software Requirements Specifications*. IEEE Std 830-1998. Nueva York: IEEE.

2. ISO/IEC/IEEE 29148:2018. *Systems and software engineering — Life cycle processes — Requirements engineering*. Ginebra: International Organization for Standardization.

**Documentos del Proyecto:**

3. [Nombre del Autor]. ([Año]). *Documento de Visión del Proyecto [Nombre del Proyecto]*. [Organización]. Versión [X.X].

4. [Nombre del Autor]. ([Año]). *Plan de Gestión del Proyecto [Nombre del Proyecto]*. [Organización].

**Documentación Técnica:**

5. [Framework/Tecnología]. ([Año]). *Documentación Oficial*. Recuperado de [URL]

6. [Base de Datos]. ([Año]). *Manual de Referencia*. Recuperado de [URL]

**Bibliografía de Referencia:**

7. Sommerville, I. (2016). *Ingeniería de Software* (10ª ed.). México: Pearson Educación.

8. Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del Software: Un Enfoque Práctico* (9ª ed.). México: McGraw-Hill Education.

**Recursos en Línea:**

9. Material del curso de Levantamiento de Requerimientos. (2025). [Universidad/Institución]. Disponible en [URL del aula virtual].

<!-- 
EJEMPLO COMPLETO PARA PROYECTO BIBLIOTECARIO:

**Estándares y Normas:**
1. IEEE Std 830-1998. Software Requirements Specifications.
2. ISO 2709:2008. Information and documentation — Format for information exchange.

**Documentos del Proyecto:**
3. Rodríguez, M. (2024). Documento de Visión - Sistema BiblioTech. Biblioteca Municipal Central.
4. González, A. (2024). Estudio de Factibilidad - Automatización de Procesos Bibliotecarios.

**Documentación Técnica:**
5. Django Framework Documentation. (2024). Disponible en: https://docs.djangoproject.com/
6. PostgreSQL 15 Documentation. (2024). Disponible en: https://www.postgresql.org/docs/15/

**Bibliografía:**
7. Lippincott, S. (2015). Library Automation in Transitional Societies: Lessons from Eastern Europe. Oxford: Chandos Publishing.
-->

[Complete esta sección con las referencias relevantes para su proyecto]

<br>

### 1.6 Resumen

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Proporcionar una sinopsis ejecutiva del contenido y organización del resto del
documento SRS.

IMPORTANCIA:
Esta sección orienta al lector sobre:
- Qué encontrará en cada sección principal
- Cómo está organizado el documento
- Dónde buscar información específica

ESTRUCTURA RECOMENDADA:
Un párrafo descriptivo por cada sección principal (Sección 2 y Sección 3),
explicando qué tipo de información contiene.

LONGITUD:
2-4 párrafos máximo. Debe ser conciso pero informativo.

EJEMPLO ACADÉMICO:
-->

Este documento de Especificación de Requisitos de Software está organizado en cuatro secciones principales que siguen el estándar IEEE 830-1998.

**La Sección 2, Descripción General**, presenta una visión global del sistema sin entrar en detalles técnicos. Incluye la perspectiva del producto dentro del contexto organizacional, un resumen de las funciones principales del sistema, las características de los diferentes tipos de usuarios que interactuarán con el sistema, y las restricciones generales bajo las cuales debe operar. También documenta las suposiciones y dependencias que podrían afectar los requisitos, así como las funcionalidades consideradas para versiones futuras.

**La Sección 3, Requisitos Específicos**, constituye el núcleo técnico del documento. Esta sección detalla exhaustivamente todos los requisitos funcionales (lo que el sistema debe hacer) y los requisitos no funcionales (cómo debe comportarse el sistema). Incluye especificaciones detalladas de las interfaces del sistema (usuario, hardware, software y comunicación), criterios de rendimiento, requisitos de seguridad, fiabilidad y disponibilidad, así como restricciones de diseño y otros atributos de calidad que el sistema debe cumplir.

**La Sección 4, Apéndices**, contiene información complementaria que respalda las secciones anteriores, incluyendo diagramas del sistema, modelos de casos de uso, glosario extendido de términos, y matrices de trazabilidad que vinculan requisitos con casos de prueba. Esta sección también puede incluir prototipos de interfaces, esquemas de bases de datos, y otros artefactos que ayudan a clarificar los requisitos especificados.

[Ajuste este resumen según la organización específica de su documento]

<br>

---

## 2 DESCRIPCIÓN GENERAL

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 2: DESCRIPCIÓN GENERAL
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO DE ESTA SECCIÓN:
Proporcionar contexto y visión general del sistema sin entrar en detalles técnicos
específicos. Esta sección ayuda a los lectores a comprender el "panorama general"
antes de sumergirse en los requisitos específicos.

IMPORTANCIA ACADÉMICA:
Esta sección establece el contexto de negocio y técnico que justifica los requisitos
específicos que vendrán en la Sección 3. Es fundamental para que stakeholders no
técnicos comprendan el propósito y las capacidades del sistema.

AUDIENCIA PRINCIPAL:
- Gerentes y ejecutivos
- Analistas de negocio
- Arquitectos de sistemas
- Nuevos miembros del equipo

PRINCIPIO CLAVE:
Todo lo descrito en la Sección 2 debe ser GENERAL. Los detalles específicos,
medibles y verificables van en la Sección 3.
-->

### 2.1 Perspectiva del producto

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Situar el sistema en su contexto más amplio: ¿Es un sistema completamente nuevo?
¿Reemplaza un sistema existente? ¿Es parte de un sistema mayor? ¿Cómo se relaciona
con otros sistemas?

QUÉ DEBE INCLUIR:

1. CONTEXTO DEL SISTEMA:
  - Si es un nuevo producto independiente, reemplazo de sistema legacy, o 
    componente de un sistema mayor
  - Relación con otros sistemas existentes en la organización

2. INTERFACES DEL SISTEMA (Vista general):
  - Interfaces con sistemas externos (NO detalles, solo mención)
  - Interfaces con hardware específico
  - Interfaces con otros componentes de software

3. DIAGRAMA DE CONTEXTO (Altamente recomendado):
  Un diagrama simple que muestre:
  - El sistema como caja central
  - Actores externos (usuarios, otros sistemas)
  - Flujos de información principales

EJEMPLO ACADÉMICO:

**Contexto del Sistema:**

BiblioTech es un sistema de información nuevo que reemplazará completamente el 
actual sistema manual de gestión bibliotecaria basado en tarjetas físicas y hojas 
de cálculo Excel. El sistema operará como una aplicación independiente pero 
compartirá cierta información con sistemas externos de la biblioteca.

BiblioTech NO es un subsistema de un sistema mayor, sino una aplicación completa 
y autónoma diseñada específicamente para las necesidades de la Biblioteca Municipal 
Central. Sin embargo, el sistema deberá integrarse con:

- Sistema de identificación de usuarios de la municipalidad (para validar datos 
  de ciudadanos)
- Sistema de correo electrónico institucional (para envío de notificaciones)
- Sistema de respaldo centralizado de la municipalidad (para backup automático)

**Relación con Sistemas Existentes:**

El sistema actual que BiblioTech reemplazará consiste en:
- Tarjetas físicas de catálogo ordenadas alfabéticamente
- Planillas Excel para control de préstamos
- Registro manual en libros de visitas
- Archivo físico de fichas de usuarios

BiblioTech digitalizará completamente estos procesos, manteniendo la misma 
lógica de negocio pero eliminando el manejo de papel.

**Interfaces del Sistema (Visión General):**

BiblioTech interactuará con:
1. **Usuarios del Sistema**: Bibliotecarios, administradores, y usuarios finales 
  (vía interfaz web)
2. **Sistemas Externos**: 
  - API del Sistema de Identificación Municipal
  - Servidor SMTP para envío de correos
  - Servidor de respaldo institucional
3. **Hardware**: 
  - Lectores de código de barras (para escaneo de libros y carnets)
  - Impresoras térmicas (para comprobantes de préstamo)
  - Servidor de base de datos

[Incluya aquí un diagrama de contexto del sistema]

ESTRUCTURA DEL DIAGRAMA DE CONTEXTO:
Puede usar notación simple con cajas y flechas. Ejemplo en texto:

┌─────────────────┐
│    Usuarios     │────┐
│   de Internet   │    │
└─────────────────┘    │
                       ▼
┌────────────────┐   ┌──────────────────────┐   ┌──────────────────┐
│ Bibliotecarios │─▶│   Sistema BiblioTech │─▶│  Sistema Email   │
└────────────────┘   └──────────────────────┘   └──────────────────┘
                              │
                              ▼
                     ┌──────────────────┐
                     │  Base de Datos   │
                     └──────────────────┘

NOTA: En su documento final, reemplace esto con un diagrama formal usando herramientas
como Draw.io, notación mermaid, Lucidchart, o similar.
-->

[Complete esta subsección describiendo la perspectiva de su producto e incluya un diagrama de contexto]

<br>

### 2.2 Funciones del producto

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
El sistema esta encargado de administrar las cuentas del restaurante, gestionar el inventario, con el fin de ayudar a minimizar perdidas y gestionar de manera eficaz el presupuesto. 

IMPORTANCIA:
El sistema propuesto es crucial para optimizar la gestión del Restaurante, asegurar el uso eficiente de subsidios, reducir el desperdicio alimentario y fortalecer la transparencia y sostenibilidad del programa de seguridad alimentaria.

NIVEL DE DETALLE:
- ALTO NIVEL:el sistema permitirá gestionar de forma integrada el control de acceso al restaurante, la identificación y categorización de usuarios, la asignación de subsidios, la planificación de menús, el control de inventarios y el registro del consumo.

ORGANIZACIÓN SUGERIDA:
Módulo de acceso y usuarios: control de ingreso, registro e identificación de categorías y subsidios.

Módulo de inventarios y menús: gestión de insumos, planificación de menús y control de desperdicios.

Módulo de consumo y trazabilidad: registro de transacciones y análisis de patrones de consumo.

Módulo de comunicación y reportes: interacción con comensales y generación de informes para la toma de decisiones.

FORMATO RECOMENDADO:
Control de acceso: permite la identificación automática de los usuarios y el registro de su ingreso al restaurante.

Gestión de usuarios y subsidios: administra las categorías de beneficiarios y asigna los subsidios correspondientes.

Gestión de inventarios: controla el ingreso, uso y disponibilidad de insumos alimentarios.

Planificación de menús: organiza menús según la demanda, disponibilidad y criterios nutricionales.

Trazabilidad del consumo: registra y analiza el consumo diario para reducir desperdicios.

Comunicación y reportes: facilita la interacción con los comensales y genera informes de gestión y desempeño.

EJEMPLO ACADÉMICO:

El Sistema UniCafe proporcionará las siguientes funciones principales:

**Gestión de Usuarios y Acceso:**

- Registro e identificación de usuarios según su categoría (estudiante, docente, administrativo, visitante).
- Control de acceso automatizado mediante credenciales institucionales o códigos QR.
- Asignación, verificación y control de subsidios según el tipo de usuario.
- Monitoreo del historial de acceso y consumo individual.

Gestión de Inventarios:
- Registro y actualización del inventario de insumos alimentarios.
- Control de entradas, salidas y vencimientos de productos.
- Alertas automáticas por bajo stock o productos próximos a expirar.
- Generación de reportes de uso y desperdicio.

Planificación de Menús:
- Creación y programación de menús diarios o semanales según disponibilidad de insumos.
 Asociación de valores nutricionales y costos estimados por menú.
- Ajuste dinámico de menús en función de la demanda y el consumo histórico.
- Publicación automatizada de menús a los comensales.

Trazabilidad y Control de Consumo:
- Registro detallado del consumo diario por usuario y por categoría.
- Seguimiento de tendencias de consumo y análisis de demanda.
- Identificación de posibles fraudes o inconsistencias en el uso de subsidios.
- Integración de datos para evaluación del impacto alimentario y operativo.

Comunicación y Notificaciones:
- Envío de notificaciones sobre disponibilidad de menús y horarios de servicio.
- Alertas personalizadas sobre uso de subsidios o incidencias en el acceso.
- Recepción de comentarios y encuestas de satisfacción de los comensales.
- Difusión de comunicados institucionales del programa de alimentación.

Reportes y Estadísticas:
- Reportes sobre consumo, subsidios aplicados, desperdicio e inventario.
- Estadísticas de asistencia y comportamiento de los usuarios.
- Indicadores de eficiencia operativa y sostenibilidad alimentaria.
- Exportación de datos para auditorías y toma de decisiones institucionales.

Administración del Sistema:
- Gestión de roles y permisos de administradores, operarios y supervisores.
- Configuración de parámetros del sistema (horarios, subsidios, umbrales de stock, etc.).
- Copia de seguridad, restauración y auditoría de operaciones.
- Integración con sistemas institucionales de datos y control.

OPCIONAL: Puede incluir un diagrama de alto nivel mostrando los módulos principales
y cómo se relacionan.

NOTA IMPORTANTE:
Esta NO es la especificación detallada de requisitos funcionales. Cada función
aquí mencionada se expandirá con requisitos específicos, medibles y verificables
en la Sección 3.1.
-->

[Complete esta subsección describiendo las funciones principales de su sistema, agrupadas lógicamente]

<br>

### 2.3 Características de los usuarios

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Identificar y describir los diferentes tipos de usuarios que interactuarán con
el sistema, incluyendo sus características relevantes que puedan afectar el diseño.

IMPORTANCIA:
Comprender a los usuarios es fundamental para:
- Diseñar interfaces apropiadas para cada perfil
- Establecer niveles adecuados de seguridad y permisos
- Determinar requisitos de capacitación
- Identificar necesidades de usabilidad y accesibilidad

QUÉ INCLUIR PARA CADA TIPO DE USUARIO:

1. Tipo de usuario (nombre del rol)
2. Descripción general del rol
3. Responsabilidades en el sistema
4. Nivel de experiencia técnica
5. Nivel de experiencia con el dominio del negocio
6. Frecuencia de uso del sistema
7. Funciones principales que utilizará
8. Necesidades especiales (accesibilidad, idioma, etc.)

FORMATO SUGERIDO:
Use una tabla o subsecciones para cada tipo de usuario.

TABLA RECOMENDADA:
-->

| Característica | Usuario Tipo 1: [Nombre del Rol] | Usuario Tipo 2: [Nombre del Rol] | Usuario Tipo 3: [Nombre del Rol] |
|----------------|-----------------------------------|-----------------------------------|-----------------------------------|
| **Descripción** | [Breve descripción del rol] | [Breve descripción del rol] | [Breve descripción del rol] |
| **Responsabilidades** | [Qué hace en el sistema] | [Qué hace en el sistema] | [Qué hace en el sistema] |
| **Nivel Técnico** | Alto/Medio/Bajo | Alto/Medio/Bajo | Alto/Medio/Bajo |
| **Experiencia en el Dominio** | Experto/Intermedio/Novato | Experto/Intermedio/Novato | Experto/Intermedio/Novato |
| **Frecuencia de Uso** | Diaria/Semanal/Ocasional | Diaria/Semanal/Ocasional | Diaria/Semanal/Ocasional |
| **Funciones Principales** | [Listar 3-5 funciones] | [Listar 3-5 funciones] | [Listar 3-5 funciones] |
| **Necesidades Especiales** | [Si aplica] | [Si aplica] | [Si aplica] |

<!-- 
EJEMPLO ACADÉMICO DETALLADO:

**TIPO DE USUARIO 1: Bibliotecario**

- **Descripción**: Personal de la biblioteca encargado de las operaciones diarias 
  de préstamos, devoluciones, y atención al público.

- **Responsabilidades en el Sistema**:
  - Registrar préstamos y devoluciones de materiales
  - Registrar nuevos usuarios
  - Procesar pagos de multas
  - Atender consultas sobre disponibilidad de materiales
  - Generar reportes básicos de operaciones diarias

- **Nivel de Experiencia Técnica**: Medio. Tienen conocimientos básicos de informática 
  pero no son expertos técnicos. Pueden manejar aplicaciones de oficina estándar.

- **Experiencia en el Dominio**: Alta. Conocen perfectamente los procesos bibliotecarios 
  y la organización de materiales. Promedio de 5+ años trabajando en bibliotecas.

- **Frecuencia de Uso**: Diaria, durante toda su jornada laboral (8 horas al día).

- **Funciones Principales que Utilizará**:
  - Módulo de préstamos y devoluciones
  - Módulo de gestión de usuarios
  - Búsqueda de materiales en catálogo
  - Gestión de reservas
  - Procesamiento de multas

- **Necesidades Especiales**: 
  - Interfaz intuitiva que permita realizar operaciones rápidamente
  - Capacidad de trabajo con interrupciones frecuentes (atención al público)
  - Acceso rápido a ayuda contextual

**TIPO DE USUARIO 2: Administrador del Sistema**

- **Descripción**: Personal técnico o jefe de biblioteca responsable de la configuración 
  y administración del sistema BiblioTech.

- **Responsabilidades en el Sistema**:
  - Configurar parámetros operativos del sistema
  - Gestionar cuentas de bibliotecarios
  - Mantener el catálogo (altas, bajas, modificaciones masivas)
  - Generar reportes estadísticos y ejecutivos
  - Realizar respaldos del sistema
  - Auditar operaciones del sistema

- **Nivel de Experiencia Técnica**: Alto. Tiene conocimientos avanzados de sistemas 
  informáticos y administración de aplicaciones.

- **Experiencia en el Dominio**: Alta. Comprende todos los procesos bibliotecarios 
  desde una perspectiva gerencial.

- **Frecuencia de Uso**: Semanal para tareas de configuración y mantenimiento, 
  diaria para consulta de reportes y auditoría.

- **Funciones Principales que Utilizará**:
  - Panel de administración completo
  - Configuración de parámetros del sistema
  - Gestión de usuarios del sistema
  - Generación de reportes avanzados
  - Herramientas de respaldo y restauración
  - Visualización de logs de auditoría

- **Necesidades Especiales**: 
  - Acceso a funciones avanzadas no disponibles para usuarios regulares
  - Herramientas de diagnóstico y monitoreo del sistema
  - Capacidad de realizar operaciones masivas sobre datos

**TIPO DE USUARIO 3: Usuario/Cliente de la Biblioteca**

- **Descripción**: Ciudadanos registrados en la biblioteca que consultan el catálogo 
  y su información personal desde Internet.

- **Responsabilidades en el Sistema**:
  - Buscar materiales disponibles en la biblioteca
  - Consultar sus préstamos activos
  - Renovar préstamos (si es posible)
  - Hacer reservas de materiales
  - Consultar su historial de préstamos

- **Nivel de Experiencia Técnica**: Bajo a Medio. Varían desde personas con 
  conocimientos básicos hasta usuarios experimentados de Internet.

- **Experiencia en el Dominio**: Baja a Media. Algunos son usuarios frecuentes 
  de bibliotecas, otros son nuevos usuarios.

- **Frecuencia de Uso**: Variable. Desde uso semanal hasta esporádico (mensual 
  o menos frecuente).

- **Funciones Principales que Utilizará**:
  - Búsqueda de materiales en catálogo
  - Consulta de cuenta personal
  - Sistema de reservas
  - Renovación de préstamos

- **Necesidades Especiales**: 
  - Interfaz muy intuitiva, sin necesidad de capacitación
  - Accesibilidad (cumplimiento WCAG 2.1 nivel AA)
  - Disponible 24/7 desde cualquier dispositivo (responsive)
  - Multiidioma (si aplica)
  - Protección de datos personales
-->

[Complete esta subsección describiendo todos los tipos de usuarios de su sistema]

<br>

### 2.4 Restricciones

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Documentar las limitaciones técnicas, operativas y normativas que puedan afectar el diseño e implementación del sistema del Restaurante Universitario UniCafé.

IMPORTANCIA:
Las restricciones son críticas para el sistema del Restaurante, ya que determinan los límites de diseño e implementación, impactan los costos y tiempos del proyecto, y deben ser identificadas desde el inicio al ser, en su mayoría, no negociables.

TIPOS COMUNES DE RESTRICCIONES:

1. Restricciones Regulatorias/Legales: cumplimiento de normas sanitarias, de manipulación de alimentos y protección de datos personales.
2. Restricciones de Hardware: dependencia de dispositivos de control de acceso, terminales de registro y equipos de cocina conectados.
3. Restricciones de Software: compatibilidad con los sistemas institucionales existentes y limitaciones en licencias o plataformas.
4. Restricciones de Interfaces con Aplicaciones: necesidad de integración con sistemas universitarios de matrícula, pagos o identificación.
5. Restricciones Paralelas (procesos concurrentes): coordinación con procesos simultáneos como el servicio de comedor y la actualización de inventarios.
6. Restricciones de Auditoría: obligación de conservar trazabilidad completa de accesos, subsidios y consumos para control institucional.
7. Restricciones de Lenguaje de Programación: alineación con los entornos tecnológicos aprobados por la universidad.
8. Restricciones de Bases de Datos: uso de motores compatibles con la infraestructura existente y políticas de respaldo establecidas.
9. Restricciones de Estándares: adopción de estándares institucionales de seguridad, usabilidad y accesibilidad.
10. Restricciones de Presupuesto y Recursos: limitaciones en financiamiento, personal técnico y tiempo de desarrollo.

FORMATO SUGERIDO:
Organice por categorías para mejor comprensión.

EJEMPLO ACADÉMICO:

**Restricciones Regulatorias y Legales:**

- El sistema DEBE cumplir con la Ley de Protección de Datos Personales vigente en Colombia (Ley 1581 de 2012) y las políticas institucionales de confidencialidad.
- Toda eliminación de datos personales DEBE realizarse de forma irreversible, respetando el derecho al olvido.
- Los registros de auditoría de accesos y consumos DEBEN conservarse por un período mínimo de dos años para fines de control institucional.
- El sistema DEBE cumplir con las normas sanitarias y de trazabilidad alimentaria exigidas por el Ministerio de Salud y la Secretaría de Salud municipal.

**Restricciones Tecnológicas:**

- El sistema DEBE ejecutarse en la infraestructura tecnológica de la universidad (servidores Linux Ubuntu Server 22.04 LTS, 8GB RAM, 500GB disco).
- DEBE ser compatible con los navegadores institucionales: Chrome 100+, Firefox 95+ y Edge 100+.
- DEBE integrarse con los dispositivos de control de acceso y lectores de tarjetas o códigos QR existentes.
- La solución DEBE funcionar en entorno web, sin requerir instalación en equipos de los operarios.

**Restricciones de Implementación:**

- El desarrollo DEBE realizarse con tecnologías open source para evitar costos de licenciamiento.
- El sistema DEBE estar en producción en un plazo máximo de seis meses desde el inicio del proyecto.
- El equipo de desarrollo ESTÁ LIMITADO a cuatro integrantes: dos desarrolladores, un analista y un tester.

**Restricciones de Interfaz:**

- El sistema DEBE integrarse con la base de datos institucional de usuarios y con el sistema de control académico (SIGA-UCP).
- DEBE utilizar el servidor de correo institucional (smtp.ucp.edu.co) para notificaciones y alertas.
- Las interfaces de comunicación DEBEN cumplir con los estándares REST y JSON definidos por el área de TI de la universidad.

**Restricciones Operacionales:**

- El sistema DEBE funcionar con la conexión a Internet existente (20 Mbps simétrica), sin posibilidad de mejora en el corto plazo.
- La base de datos DEBE SER PostgreSQL versión 13 o superior, conforme al estándar institucional.
- El sistema NO PUEDE requerir instalación local en los equipos del personal administrativo ni de los comensales.

**Restricciones de Migración de Datos:**

- El sistema DEBE permitir importar datos históricos de usuarios, subsidios y registros de consumo provenientes de hojas de cálculo y archivos CSV.
- La migración de datos NO PUEDE interrumpir el servicio del restaurante por más de cuatro horas.

**Restricciones de Capacitación:**

- La capacitación del personal operativo DEBE completarse en un máximo de 16 horas (dos jornadas de ocho horas).
- Los materiales de capacitación DEBEN estar en español y adaptados a los perfiles técnicos del personal.

**Restricciones Presupuestarias:**

- El presupuesto total del proyecto NO PUEDE superar los $25,000 USD o su equivalente en pesos colombianos.
- NO SE PUEDE ampliar el equipo de trabajo; el desarrollo debe realizarse con el personal asignado institucionalmente.

NOTA IMPORTANTE:
Sea específico. NO escriba "el sistema debe ser rápido" (eso es un requisito de 
rendimiento). Escriba restricciones concretas como "el sistema debe ejecutarse 
en servidores con máximo 8GB de RAM".
-->

[Complete esta subsección documentando todas las restricciones aplicables a su proyecto]

<br>

### 2.5 Suposiciones y dependencias

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Documentar todas las suposiciones (assumptions) hechas durante la especificación
de requisitos y las dependencias externas que podrían afectar el desarrollo o
funcionamiento del sistema.

IMPORTANCIA CRÍTICA:
- Las suposiciones son premisas que SE ASUMEN CIERTAS pero que podrían cambiar
- Si una suposición resulta incorrecta, los requisitos pueden necesitar revisión
- Las dependencias son factores externos fuera del control del equipo
- Identificarlas permite gestión de riesgos proactiva

DIFERENCIA CLAVE:
- SUPOSICIÓN: "Se asume que el usuario tiene conexión a Internet"
- DEPENDENCIA: "El sistema depende de la disponibilidad de la API externa X"

CATEGORÍAS COMUNES:

1. Suposiciones sobre Usuarios
2. Suposiciones sobre el Entorno de Operación
3. Suposiciones sobre Datos
4. Dependencias de Sistemas Externos
5. Dependencias de Terceros
6. Dependencias Tecnológicas

FORMATO SUGERIDO:
Liste cada suposición/dependencia numerada para fácil referencia.

EJEMPLO ACADÉMICO:

**Suposiciones:**

1. **Conectividad**: Se asume que la biblioteca cuenta con conexión a Internet 
  estable y continua durante el horario de operación. Si la conexión falla, 
  algunas funcionalidades no estarán disponibles.

2. **Hardware**: Se asume que las computadoras de las estaciones de trabajo de 
  bibliotecarios cumplen con los requisitos mínimos: procesador dual-core 2GHz, 
  4GB RAM, navegador web actualizado.

3. **Conocimientos del Personal**: Se asume que el personal de biblioteca tiene 
  conocimientos básicos de informática (uso de navegador web, mouse, teclado) 
  y que recibirá capacitación específica sobre BiblioTech antes del lanzamiento.

4. **Proceso de Negocio**: Se asume que los procesos bibliotecarios actuales 
  (políticas de préstamo, cálculo de multas, categorización de materiales) 
  continuarán siendo válidos en el sistema digitalizado.

5. **Volumen de Datos Inicial**: Se asume que el catálogo inicial contiene 
  aproximadamente 25,000 materiales bibliográficos y 15,000 usuarios registrados, 
  con un crecimiento anual estimado del 10%.

6. **Usuarios Finales**: Se asume que los usuarios de la biblioteca que accedan 
  al catálogo en línea tienen conocimientos básicos de navegación web y acceso 
  a un dispositivo con navegador (computadora, tablet, smartphone).

7. **Datos de Migración**: Se asume que los datos en Excel del sistema actual 
  están razonablemente limpios y estructurados, y que cualquier inconsistencia 
  será resuelta antes de la migración.

8. **Apoyo Institucional**: Se asume que la dirección de la biblioteca y la 
  municipalidad proporcionarán el apoyo necesario para la adopción del sistema, 
  incluyendo tiempo para capacitación del personal.

9. **Mantenimiento**: Se asume que la municipalidad proporcionará soporte técnico 
  continuo para el servidor y la infraestructura de red.

**Dependencias:**

1. **Sistema Municipal de Identificación (SMI)**: El módulo de registro de usuarios 
  DEPENDE de la disponibilidad y correcto funcionamiento de la API del SMI para 
  validar identidad de ciudadanos. Si la API no está disponible, el registro de 
  nuevos usuarios se verá afectado.

2. **Servicio de Correo Electrónico**: El módulo de notificaciones DEPENDE del 
  servidor SMTP institucional (mail.municipalidad.gob). Si el servicio de correo 
  falla, las notificaciones automáticas no se enviarán.

3. **Proveedor de Hosting**: El sistema DEPENDE de la infraestructura de servidores 
  de la municipalidad. Cualquier mantenimiento, actualización o problema en esta 
  infraestructura afectará la disponibilidad de BiblioTech.

4. **Código de Barras**: El sistema DEPENDE del estándar ISBN (International Standard 
  Book Number) para identificación de libros. Materiales sin ISBN requerirán 
  códigos alternativos generados internamente.

5. **Navegadores Web**: El sistema DEPENDE de que los navegadores web mantengan 
  compatibilidad con los estándares HTML5, CSS3 y JavaScript ES6. Cambios 
  significativos en navegadores podrían requerir actualizaciones del sistema.

6. **Base de Datos PostgreSQL**: El sistema DEPENDE de PostgreSQL y sus 
  actualizaciones de seguridad. Migraciones a nuevas versiones mayores de 
  PostgreSQL requerirán pruebas exhaustivas.

7. **Lectores de Código de Barras**: El sistema DEPENDE de los lectores de código 
  de barras Zebra DS2208. Si se reemplazan por otro modelo, puede requerirse 
  adaptación del sistema.

8. **Proveedor de Carnes de Biblioteca**: La funcionalidad de escaneado de carnets 
  DEPENDE de que el proveedor de carnets imprima códigos de barras legibles según 
  el estándar Code 39 o similar.

9. **Equipo de Desarrollo**: El cronograma del proyecto DEPENDE de la disponibilidad 
  continua del equipo de desarrollo asignado. Cambios en el equipo podrían afectar 
  plazos de entrega.

10. **Aprobaciones de la Municipalidad**: Ciertas decisiones de diseño y configuración 
  DEPENDEN de aprobaciones del departamento de sistemas de la municipalidad, lo 
  que podría introducir retrasos si las aprobaciones se demoran.

**Impacto de Cambios:**

Si cualquiera de las suposiciones anteriores resulta incorrecta o las dependencias 
externas fallan, se requerirá:
- Revisión de requisitos afectados
- Evaluación de impacto en cronograma y presupuesto
- Posible renegociación de alcance del proyecto

El equipo de proyecto debe monitorear continuamente la validez de estas suposiciones 
y el estado de las dependencias, reportando cualquier cambio significativo a los 
stakeholders.

NOTA PARA ESTUDIANTES:
En proyectos reales, este análisis es crítico para la gestión de riesgos. Una 
suposición incorrecta puede hacer que todo un proyecto fracase. Sea honesto y 
exhaustivo al documentar suposiciones y dependencias.
-->

[Complete esta subsección documentando todas las suposiciones y dependencias de su proyecto]

<br>

### 2.6 Requisitos futuros

<!-- 
OBJETIVO DE ESTA SUBSECCIÓN:
Documentar las funcionalidades y mejoras que no serán incluidas en la versión inicial del sistema de gestión del Restaurante Universitario UniCafé, pero que se consideran valiosas para futuras versiones orientadas a ampliar su alcance, eficiencia y sostenibilidad.

IMPORTANCIA:
Permite definir qué funciones no estarán en la versión inicial, orientar la evolución futura del sistema y conservar ideas útiles para próximas versiones.

CATEGORÍAS SUGERIDAS:
1. Funcionalidades nuevas: incorporación de módulos avanzados para análisis nutricional, control de proveedores y evaluación de impacto alimentario.
2. Integraciones adicionales: conexión con sistemas financieros, plataformas móviles y aplicaciones institucionales de bienestar universitario.
3. Mejoras de rendimiento: optimización del procesamiento de datos, tiempos de respuesta y capacidad para manejar mayor volumen de usuarios.
4. Mejoras de usabilidad: diseño de interfaces más intuitivas y accesibles para personal operativo y comensales.
5. Soporte de nuevas plataformas: compatibilidad con dispositivos móviles, terminales de autoservicio y sistemas de pago electrónico.

FORMATO:
Liste de manera concisa. NO desarrolle requisitos completos aquí.

PRINCIPIO IMPORTANTE:
Estos requisitos fueron deliberadamente EXCLUIDOS del alcance actual por razones
de tiempo, presupuesto, o prioridad. NO son errores ni omisiones.

EJEMPLO ACADÉMICO:

**Funcionalidades Futuras Planificadas:**

**Versión 2.0 (Estimada para 12 meses después del lanzamiento):**

1. **Aplicación Móvil Nativa**: desarrollo de una app para Android e iOS que permita a los usuarios consultar menús, registrar consumos y recibir notificaciones personalizadas.

2. **Sistema de Recomendaciones**:permitir a los comensales reservar su porción o menú con antelación para reducir desperdicios.

3. **Biblioteca Digital**: análisis automático del valor nutricional de los menús ofrecidos y recomendaciones personalizadas.

4. **Sistema de Comentarios y Reseñas**: asignación de puntos o beneficios por hábitos alimentarios saludables o consumo responsable.

5. **Integración con Redes Sociales**: visualización del historial de consumo, subsidios utilizados y estadísticas personales.

**Versión 2.5 (Estimada para 18 meses):**

6. **Préstamo Interbibliotecario**: módulo para gestión de compras, cotizaciones y trazabilidad de productos desde su origen.

7. **Sistema de Eventos**: tablero ejecutivo con indicadores predictivos de demanda, desperdicio y eficiencia del subsidio.

8. **Analítica Avanzada**: recopilación y análisis de opiniones de los comensales para ajustar menús y servicios.

9. **Portal del Autor**: registro y reporte del impacto ambiental del consumo (huella alimentaria, emisiones, residuos).

10. **Accesibilidad Mejorada**: notificaciones automáticas sobre lotes o productos con riesgo sanitario o vencimiento próximo.

**Integraciones Futuras:**

11. **Sistema de Pago en Línea**: integración con pasarelas de pago institucionales y billeteras digitales para compras fuera del subsidio.

12. **API Pública**: exposición de una API REST para interoperar con otros sistemas universitarios (bienestar, finanzas, registro académico).

13. **Integración con Servicios Editoriales**: conexión con Moodle o sistemas de bienestar estudiantil para gestión unificada de beneficios.

**Mejoras Tecnológicas Consideradas:**

14. **Modo Offline**: permitir operaciones básicas de control de acceso y registro de consumo sin conexión, con sincronización posterior.

15. **Reconocimiento por Voz**: autenticación biométrica de usuarios para agilizar el ingreso y reducir fraudes.

16. **Chatbot de Atención**: asistente virtual que brinde información sobre menús, horarios y subsidios.

17. **Realidad Aumentada**: recomendaciones automáticas de menús basadas en consumo, nutrición y preferencias.

**Nota Importante:**
Estos requisitos futuros son tentativos y están sujetos a disponibilidad de 
presupuesto, cambios en prioridades del negocio, y evolución tecnológica. No 
constituyen compromisos contractuales.

CONSIDERACIÓN ARQUITECTÓNICA:
Aunque estas funcionalidades no se implementarán en la versión 1.0, la arquitectura del sistema del Restaurante debe diseñarse de forma modular y escalable, permitiendo su incorporación futura sin requerir rediseños significativos. Esto implica:

- Diseño modular: cada módulo (usuarios, inventario, menús, consumo, reportes) debe ser independiente y extensible.
- APIs bien definidas: los componentes del sistema deben comunicarse mediante interfaces estandarizadas y documentadas.
- Base de datos extensible: el modelo de datos debe admitir nuevas entidades y relaciones sin afectar la estructura principal.
- Separación clara de responsabilidades: garantizar que la lógica de negocio, la presentación y el acceso a datos estén desacoplados para facilitar mantenimiento y evolución.

PROCESO DE PRIORIZACIÓN:
Los requisitos y funcionalidades futuras del sistema serán evaluados y priorizados en cada ciclo de planificación, considerando los siguientes criterios:

- Retroalimentación de los usuarios y personal operativo tras la implementación inicial.
- Cambios en el contexto institucional o en las políticas de bienestar universitario.
- Disponibilidad de recursos técnicos y financieros para el desarrollo.
- Retorno de inversión (ROI) esperado en términos de eficiencia, reducción de desperdicio o mejora del servicio.
- Dependencias técnicas con otros módulos o sistemas institucionales.
-->

[Complete esta subsección con los requisitos futuros identificados para su proyecto]

<br>

---

## 3 REQUISITOS ESPECÍFICOS

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 3: REQUISITOS ESPECÍFICOS
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO DE ESTA SECCIÓN:
Esta es la sección MÁS IMPORTANTE del documento SRS. Aquí se especifican de manera
DETALLADA, PRECISA y VERIFICABLE todos los requisitos del sistema.

IMPORTANCIA CRÍTICA:
- Es la base para el diseño, implementación y pruebas del sistema
- Debe ser lo suficientemente detallada para que desarrolladores puedan construir 
  el sistema sin ambigüedades
- Debe ser lo suficientemente precisa para que testers puedan verificar cada 
  requisito
- Sirve como contrato entre cliente y equipo de desarrollo

PRINCIPIOS FUNDAMENTALES PARA REQUISITOS DE CALIDAD:

Un requisito de calidad es:

1. CORRECTO: Refleja una necesidad real del cliente/usuario
2. NO AMBIGUO: Tiene una sola interpretación posible
3. COMPLETO: Contiene toda la información necesaria para su implementación
4. CONSISTENTE: No contradice otros requisitos
5. CLASIFICADO: Tiene prioridad asignada (esencial/deseable/opcional)
6. VERIFICABLE: Se puede diseñar una prueba para verificar su cumplimiento
7. MODIFICABLE: Estructura que permite cambios sin afectar otros requisitos
8. TRAZABLE: Tiene ID único y se puede seguir a través del ciclo de vida

PALABRAS CLAVE IEEE 830:
En requisitos, use estas palabras con precisión:
- DEBE / DEBERÁ (MUST): Requisito obligatorio, esencial
- DEBERÍA (SHOULD): Requisito deseable, importante pero no crítico
- PUEDE (MAY): Requisito opcional

ERRORES COMUNES A EVITAR:

✗ Requisitos ambiguos: "El sistema será rápido"
✓ Requisito correcto: "El sistema responderá a consultas en máximo 3 segundos"

✗ Requisitos sin verificar: "El sistema será fácil de usar"
✓ Requisito correcto: "El 90% de usuarios podrán completar un préstamo sin ayuda 
  después de 30 minutos de capacitación"

✗ Requisitos que especifican soluciones: "El sistema usará base de datos MySQL"
  (a menos que sea una restricción real)
✓ Requisito correcto: "El sistema almacenará datos de forma persistente y permitirá 
  consultas concurrentes de al menos 50 usuarios"

✗ Requisitos que combinan múltiples funcionalidades sin separación clara

ORGANIZACIÓN DE ESTA SECCIÓN:
La Sección 3 puede organizarse de diferentes formas según IEEE 830:
- Por funcionalidad del sistema
- Por tipo de usuario
- Por modo de operación
- Por objetos del sistema

Esta plantilla usa organización por TIPO DE REQUISITO (funcionales, no funcionales,
interfaces, etc.) que es la más común en proyectos académicos.
-->

### 3.1 Requisitos funcionales

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS FUNCIONALES
═══════════════════════════════════════════════════════════════════════════════

DEFINICIÓN:
Los requisitos funcionales describen QUÉ debe HACER el sistema. Son las funciones,
servicios, o comportamientos que el sistema debe proporcionar.

DIFERENCIA CON CASOS DE USO:
- REQUISITO FUNCIONAL: "El sistema debe validar las credenciales del usuario"
- CASO DE USO: Describe el flujo completo de interacción (incluyendo flujos 
  alternativos, excepciones, pre y post condiciones)

Los casos de uso PUEDEN incluirse en los Apéndices (4.1), pero aquí se documentan
los requisitos funcionales de forma atómica.

FORMATO ESTÁNDAR PARA CADA REQUISITO:

Use una tabla como la siguiente para cada requisito funcional:
-->

**PLANTILLA DE REQUISITO FUNCIONAL:**

| **ID** | RF-XXX |
|--------|--------|
| **Nombre** | [Nombre corto descriptivo del requisito] |
| **Descripción** | [Descripción detallada y precisa de la funcionalidad. Use lenguaje claro, sin ambigüedades. Especifique inputs, procesamiento, y outputs esperados.] |
| **Prioridad** | Esencial / Deseable / Opcional |
| **Estabilidad** | Alta / Media / Baja |
| **Fuente** | [Stakeholder que solicitó este requisito] |
| **Criterios de Aceptación** | 1. [Criterio medible 1]<br>2. [Criterio medible 2]<br>3. [Criterio medible 3] |
| **Dependencias** | [RF-XXX, RF-YYY] o "Ninguna" |
| **Comentarios** | [Cualquier información adicional relevante] |

<!-- 
EXPLICACIÓN DE CADA CAMPO:

- **ID**: Identificador único (RF-001, RF-002, etc.). Use números secuenciales.
  CRÍTICO para trazabilidad.

- **Nombre**: Título breve que identifique el requisito (max 8-10 palabras)

- **Descripción**: La especificación completa del requisito. DEBE ser:
  - Clara: Lenguaje preciso, sin términos vagos
  - Completa: Incluir toda la información necesaria
  - Verificable: Debe poder probarse
  - Consistente: No contradecir otros requisitos
  
  Template para descripciones:
  "El sistema DEBE [acción] [entidad/datos] [bajo qué condiciones] 
  [con qué restricciones/validaciones]"

- **Prioridad**:
  - Esencial: El sistema no puede funcionar sin esto. DEBE estar en v1.0
  - Deseable: Importante pero el sistema puede funcionar sin ello temporalmente
  - Opcional: Nice to have, puede postergarse a versiones futuras

- **Estabilidad**: Qué tan probable es que este requisito cambie:
  - Alta: Requisito bien entendido, poco probable que cambie
  - Media: Puede requerir refinamiento
  - Baja: Requisito exploratorio, probablemente cambiará

- **Fuente**: Quién solicitó este requisito (cliente, usuario, regulación, etc.)

- **Criterios de Aceptación**: Condiciones específicas, medibles y verificables 
  que deben cumplirse para que el requisito se considere implementado correctamente.
  Estos serán la base de los casos de prueba.

- **Dependencias**: Otros requisitos que deben implementarse antes o junto con 
  este requisito.

- **Comentarios**: Cualquier aclaración adicional, nota técnica, o contexto

ORGANIZACIÓN DE REQUISITOS FUNCIONALES:

Agrupe los requisitos por módulos funcionales del sistema. Por ejemplo:

3.1.1 Módulo de Autenticación y Autorización
3.1.2 Módulo de Gestión de Usuarios
3.1.3 Módulo de Gestión de Catálogo
3.1.4 Módulo de Préstamos y Devoluciones
3.1.5 Módulo de Reportes
... etc

Dentro de cada módulo, liste todos los requisitos funcionales relacionados.

EJEMPLOS ACADÉMICOS COMPLETOS:
-->

#### 3.1.1 Módulo de Autenticación y Seguridad

<!-- 
Este módulo incluye todos los requisitos relacionados con login, logout, gestión
de sesiones, permisos, y seguridad de acceso al sistema.
-->

| **ID** | RF-001 |
|--------|--------|
| **Nombre** | Autenticación de usuarios del sistema |
| **Descripción** | El sistema DEBE proporcionar una interfaz de login que permita a usuarios autorizados (bibliotecarios y administradores) autenticarse mediante credenciales únicas. El sistema DEBE validar nombre de usuario y contraseña contra la base de datos de usuarios del sistema. Si las credenciales son correctas, el sistema DEBE crear una sesión autenticada y redirigir al usuario al panel principal. Si las credenciales son incorrectas, el sistema DEBE mostrar un mensaje de error genérico ("Usuario o contraseña incorrectos") sin especificar cuál de los dos es incorrecto (por seguridad). |
| **Prioridad** | Esencial |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento de seguridad estándar |
| **Criterios de Aceptación** | 1. Un usuario con credenciales válidas puede acceder al sistema<br>2. Un usuario con credenciales inválidas NO puede acceder y ve mensaje de error<br>3. El mensaje de error no revela si el usuario existe o la contraseña es incorrecta<br>4. La contraseña se transmite de forma encriptada (HTTPS)<br>5. La contraseña se almacena hasheada en la base de datos (bcrypt o similar) |
| **Dependencias** | Ninguna |
| **Comentarios** | Implementar bloqueo temporal de cuenta después de 5 intentos fallidos consecutivos (ver RF-002). Este requisito NO incluye autenticación de usuarios finales (clientes de la biblioteca), solo personal del sistema. |
<br>

| **ID** | RF-002 |
|--------|--------|
| **Nombre** | Bloqueo de cuenta por intentos fallidos |
| **Descripción** | El sistema DEBE bloquear temporalmente una cuenta de usuario después de 5 intentos fallidos de autenticación consecutivos. El bloqueo DEBE durar 30 minutos. Durante el período de bloqueo, el sistema DEBE mostrar el mensaje "Cuenta temporalmente bloqueada por seguridad. Intente nuevamente en X minutos" donde X es el tiempo restante. El sistema DEBE enviar notificación por correo electrónico al usuario informando del bloqueo. Después de 30 minutos, el contador de intentos fallidos DEBE resetearse automáticamente. Un administrador DEBE poder desbloquear manualmente una cuenta antes de que expire el tiempo. |
| **Prioridad** | Esencial |
| **Estabilidad** | Alta |
| **Fuente** | Requerimiento de seguridad - Cliente |
| **Criterios de Aceptación** | 1. Después de 5 intentos fallidos, el sistema bloquea la cuenta<br>2. Durante el bloqueo, no se permite autenticación incluso con credenciales correctas<br>3. Se muestra mensaje con tiempo restante de bloqueo<br>4. Se envía email de notificación al usuario<br>5. Después de 30 minutos, el bloqueo se levanta automáticamente<br>6. Un administrador puede desbloquear manualmente<br>7. Los intentos fallidos se registran en el log de auditoría |
| **Dependencias** | RF-001 (Autenticación de usuarios) |
| **Comentarios** | Los intentos fallidos se cuentan POR cuenta de usuario, no por dirección IP. Esto previene ataques de fuerza bruta pero también protege al usuario legítimo. |
<br>

| **ID** | RF-003 |
|--------|--------|
| **Nombre** | Control de acceso basado en roles (RBAC) |
| **Descripción** | El sistema DEBE implementar control de acceso basado en roles. DEBEN existir al menos tres roles: Administrador, Bibliotecario, y Asistente. Cada rol DEBE tener permisos específicos para acceder a diferentes módulos y funciones del sistema. Un usuario con rol Administrador DEBE tener acceso completo a todas las funcionalidades. Un usuario con rol Bibliotecario DEBE tener acceso a funciones operativas (préstamos, devoluciones, búsqueda, registro de usuarios) pero NO a configuración del sistema ni reportes gerenciales. Un usuario con rol Asistente DEBE tener acceso solo a funciones de consulta (búsqueda de catálogo y consulta de usuarios) sin permisos de modificación. El sistema DEBE denegar el acceso a funcionalidades no autorizadas mostrando mensaje "No tiene permisos para realizar esta acción". |
| **Prioridad** | Esencial |
| **Estabilidad** | Media |
| **Fuente** | Cliente - Jefe de Biblioteca |
| **Criterios de Aceptación** | 1. Se pueden definir al menos 3 roles diferentes con permisos distintos<br>2. Los permisos se verifican en cada operación del sistema<br>3. Intentos de acceso no autorizado son bloqueados con mensaje apropiado<br>4. Los permisos de cada rol están claramente documentados<br>5. Los intentos de acceso no autorizado se registran en log de auditoría<br>6. Un administrador puede modificar permisos de roles (requisito futuro - documentar en 2.6) |
| **Dependencias** | RF-001 (Autenticación de usuarios) |
| **Comentarios** | La asignación de rol a un usuario se realiza durante la creación de la cuenta por un Administrador. Un usuario solo puede tener un rol a la vez en esta versión. Versiones futuras podrían permitir roles múltiples. |
<br>

#### 3.1.2 Módulo de Gestión de Usuarios (Clientes de la Biblioteca)

<!-- 
Este módulo gestiona los usuarios FINALES de la biblioteca (no el personal).
Incluye registro, actualización, consulta, suspensión de usuarios.
-->

| **ID** | RF-010 |
|--------|--------|
| **Nombre** | Registro de nuevo usuario de biblioteca |
| **Descripción** | El sistema DEBE permitir a un Bibliotecario o Administrador registrar un nuevo usuario de biblioteca. El sistema DEBE capturar los siguientes datos obligatorios: nombres, apellidos, tipo de documento (Cédula/Pasaporte), número de documento, fecha de nacimiento, dirección, teléfono, correo electrónico, y categoría de usuario (Adulto/Estudiante/Infantil). El sistema DEBE validar que el número de documento sea único en el sistema. El sistema DEBE validar que el correo electrónico tenga formato válido. El sistema DEBE calcular automáticamente la fecha de expiración de la membresía (1 año desde fecha de registro). El sistema DEBE generar automáticamente un número único de carnet de biblioteca. El sistema DEBE permitir capturar opcionalmente: segundo teléfono, y observaciones. Al confirmar el registro, el sistema DEBE mostrar el número de carnet generado y DEBE permitir imprimir una ficha de registro. |
| **Prioridad** | Esencial |
| **Estabilidad** | Alta |
| **Fuente** | Cliente - Bibliotecarios |
| **Criterios de Aceptación** | 1. Se pueden registrar usuarios con todos los datos obligatorios<br>2. El sistema rechaza registro con documento duplicado<br>3. El sistema valida formato de email<br>4. El sistema genera número de carnet único y consecutivo<br>5. La fecha de expiración se calcula correctamente (fecha actual + 1 año)<br>6. Se puede imprimir ficha de registro con código de barras del carnet<br>7. El número de carnet comienza con prefijo configurable (ej: "BMUN-")|
| **Dependencias** | RF-003 (Control de acceso - solo Bibliotecario y Admin pueden registrar)<br>RF-011 (Validación con Sistema Municipal - si está disponible) |
| **Comentarios** | La categoría de usuario determina las políticas de préstamo aplicables (cantidad de materiales, días de préstamo). Ver RF-030 para políticas de préstamo. Si existe integración con Sistema Municipal de Identificación, se debe validar que el documento es válido (ver RF-011). |
<br>

| **ID** | RF-011 |
|--------|--------|
| **Nombre** | Validación de identidad con Sistema Municipal |
| **Descripción** | El sistema DEBE integrarse con la API del Sistema de Identificación Municipal (SMI) para validar la identidad del ciudadano durante el registro. Cuando el usuario ingresa tipo y número de documento, el sistema DEBE consultar la API del SMI. Si el documento es válido, el sistema DEBE auto-completar nombres, apellidos, y fecha de nacimiento con los datos oficiales del SMI. Si el documento no es válido o no se encuentra en el SMI, el sistema DEBE mostrar una advertencia pero DEBE permitir continuar con el registro manual (el bibliotecario puede verificar físicamente el documento). Si la API del SMI no está disponible (timeout, error de conexión), el sistema DEBE permitir registro manual mostrando un mensaje: "No se pudo verificar con Sistema Municipal. Proceda con verificación manual del documento." |
| **Prioridad** | Deseable |
| **Estabilidad** | Media |
| **Fuente** | Requerimiento de integración - Municipalidad |
| **Criterios de Aceptación** | 1. El sistema consulta la API del SMI al ingresar documento<br>2. Si el documento es válido, se auto-completan datos<br>3. Si el documento es inválido, se muestra advertencia pero se permite continuar<br>4. Si la API no responde en 5 segundos (timeout), se permite registro manual<br>5. Todos los intentos de validación se registran en log del sistema<br>6. Los datos auto-completados son editables por el bibliotecario |
| **Dependencias** | RF-010 (Registro de usuario)<br>Disponibilidad de API del Sistema Municipal de Identificación v2.1 |
| **Comentarios** | Este requisito es DESEABLE, no ESENCIAL, porque el sistema debe poder funcionar aunque la integración con SMI no esté disponible. La API del SMI es un sistema externo fuera del control del proyecto. Documentar timeout y manejo de errores claramente. |
<br>

**[Continúe con más requisitos funcionales del Módulo de Gestión de Usuarios: actualización de datos, consulta de usuarios, suspensión de usuarios, renovación de membresía, etc.]**

#### 3.1.3 Módulo de Gestión de Catálogo

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.4 Módulo de Préstamos y Devoluciones

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.5 Módulo de Reservas

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.6 Módulo de Multas y Pagos

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.7 Módulo de Notificaciones

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.8 Módulo de Reportes y Estadísticas

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.9 Módulo de Administración del Sistema

<!-- Continúe documentando requisitos para este módulo -->

#### 3.1.10 Módulo de Auditoría y Logs

<!-- Continúe documentando requisitos para este módulo -->

<!-- 
CHECKLIST DE CALIDAD PARA REQUISITOS FUNCIONALES:

Antes de dar por terminado un requisito funcional, verifique:

☐ Tiene un ID único y secuencial
☐ Tiene un nombre descriptivo
☐ La descripción es clara y sin ambigüedades
☐ Usa las palabras clave correctamente (DEBE/DEBERÍA/PUEDE)
☐ Es verificable (se puede probar)
☐ Tiene prioridad asignada
☐ Tiene criterios de aceptación medibles
☐ Las dependencias están identificadas
☐ No contradice otros requisitos
☐ No especifica soluciones técnicas innecesariamente (a menos que sea una restricción)
☐ Es atómico (no combina múltiples funcionalidades que deberían ser requisitos separados)

CANTIDAD DE REQUISITOS:

NO hay un número "correcto" de requisitos. Depende de la complejidad del sistema.
Como referencia:
- Sistema pequeño: 30-60 requisitos funcionales
- Sistema mediano: 60-150 requisitos funcionales
- Sistema grande: 150+ requisitos funcionales

Un sistema como BiblioTech (biblioteca mediana) típicamente tendría 80-120 
requisitos funcionales bien especificados.

IMPORTANTE PARA ESTUDIANTES:

En proyectos académicos, es mejor tener MENOS requisitos pero MUY BIEN ESPECIFICADOS
que muchos requisitos vagos o incompletos. La calidad supera a la cantidad.

Si su proyecto es académico y tiene límites de tiempo, enfóquese en:
1. Especificar completamente los módulos principales (2-3 módulos)
2. Para módulos secundarios, puede listar requisitos de forma más resumida
3. Demuestre que entiende CÓMO escribir requisitos de calidad
-->

---

### 3.2 Requisitos de interfaz externa

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS DE INTERFAZ EXTERNA
═══════════════════════════════════════════════════════════════════════════════

DEFINICIÓN:
Los requisitos de interfaz externa describen CÓMO el sistema interactúa con
su entorno: usuarios (UI), hardware, otros sistemas (software), y redes (comunicación).

IMPORTANCIA:
Las interfaces son puntos críticos de falla. Una interfaz mal especificada puede
hacer que todo el sistema sea inutilizable incluso si la lógica interna es perfecta.

CATEGORÍAS:
3.2.1 Interfaz de Usuario (UI)
3.2.2 Interfaz de Hardware
3.2.3 Interfaz de Software
3.2.4 Interfaz de Comunicación
-->

#### 3.2.1 Interfaz de usuario

<!-- 
OBJETIVO:
Especificar características de las interfaces gráficas o de línea de comando
que los usuarios utilizarán para interactuar con el sistema.

QUÉ INCLUIR:
- Estándares de GUI (Material Design, Bootstrap, etc.)
- Resoluciones de pantalla soportadas
- Navegadores web soportados
- Accesibilidad
- Idiomas
- Layouts generales
- Flujos de navegación principales

QUÉ NO INCLUIR AQUÍ:
Mockups detallados de cada pantalla (esos van en Apéndices o documentos de diseño).
Aquí se especifican CARACTERÍSTICAS GENERALES de la UI.
-->

**RUI-001: Estándar de interfaz web responsiva**

El sistema DEBE proporcionar una interfaz web responsiva basada en HTML5, CSS3 y JavaScript. La interfaz DEBE adaptarse automáticamente a diferentes tamaños de pantalla:
- Escritorio: Resoluciones desde 1024x768 hasta 1920x1080 píxeles
- Tablet: Resoluciones desde 768x1024 hasta 1024x1366 píxeles
- Móvil: Resoluciones desde 320x568 hasta 428x926 píxeles

La interfaz DEBE seguir principios de diseño Material Design o Bootstrap para consistencia visual. Los elementos de navegación DEBEN reorganizarse apropiadamente en dispositivos móviles (menú hamburguesa, controles táctiles más grandes, etc.).

**RUI-002: Compatibilidad de navegadores**

El sistema DEBE funcionar correctamente en los siguientes navegadores web:
- Google Chrome versión 90 o superior
- Mozilla Firefox versión 88 o superior
- Microsoft Edge versión 90 o superior
- Safari versión 14 o superior (para usuarios de macOS/iOS)

El sistema DEBE detectar navegadores no soportados y mostrar un mensaje informativo sugiriendo actualizar o cambiar de navegador.

**RUI-003: Accesibilidad (WCAG 2.1 Nivel AA)**

La interfaz de usuario DEBE cumplir con las pautas WCAG 2.1 Nivel AA para garantizar accesibilidad a usuarios con discapacidades:

- **Contraste de color**: Relación de contraste mínima de 4.5:1 para texto normal y 3:1 para texto grande
- **Navegación por teclado**: Todas las funcionalidades DEBEN ser accesibles usando solo teclado (sin mouse)
- **Etiquetas ARIA**: Elementos interactivos DEBEN tener atributos ARIA apropiados
- **Texto alternativo**: Todas las imágenes funcionales DEBEN tener texto alternativo descriptivo
- **Tamaño de fuente**: El usuario DEBE poder aumentar el tamaño de texto hasta 200% sin pérdida de funcionalidad
- **Indicadores de foco**: Elementos enfocados DEBEN tener indicador visual claro
- **Lectores de pantalla**: La interfaz DEBE ser compatible con lectores de pantalla (JAWS, NVDA, VoiceOver)

**RUI-004: Idioma de la interfaz**

El sistema DEBE proporcionar interfaz en idioma español. Todos los mensajes del sistema, etiquetas de campos, botones, mensajes de error, y ayuda contextual DEBEN estar en español.

La interfaz DEBE usar terminología clara y consistente en todo el sistema. Por ejemplo, si se usa "Usuario" en un lugar, no usar "Cliente" en otro lugar para referirse a lo mismo.

REQUISITO FUTURO: Soporte multiidioma (inglés, portugués) - Ver sección 2.6.

**RUI-005: Mensajes de error y retroalimentación**

El sistema DEBE proporcionar mensajes de error claros, específicos y accionables:
- Los mensajes DEBEN indicar QUÉ salió mal
- Los mensajes DEBEN indicar CÓMO corregir el error
- Los mensajes NO DEBEN exponer información técnica sensible (stack traces, queries SQL)
- Los mensajes de error DEBEN usar color rojo e icono de advertencia
- Los mensajes de éxito DEBEN usar color verde e icono de confirmación
- Los mensajes informativos DEBEN usar color azul e icono de información

Ejemplo de mensaje de error correcto:
✓ "El número de documento ya está registrado. Verifique que el documento sea correcto o busque el usuario existente."

Ejemplo de mensaje de error incorrecto:
✗ "Error: Duplicate entry '12345678' for key 'users.documento'"

**RUI-006: Tiempo de espera y sesión**

El sistema DEBE mostrar indicadores visuales de carga (spinners, barras de progreso) durante operaciones que tomen más de 1 segundo.

La sesión de usuario DEBE expirar después de 30 minutos de inactividad. Dos minutos antes de la expiración, el sistema DEBE mostrar un modal de advertencia con opción de "Continuar sesión" o "Cerrar sesión". Si el usuario no responde, el sistema DEBE cerrar la sesión automáticamente y redirigir a la página de login.

**RUI-007: Navegación y estructura de menú**

La interfaz DEBE tener una barra de navegación principal consistente en todas las páginas con acceso a:
- Inicio / Panel principal
- Préstamos y devoluciones
- Búsqueda de catálogo
- Gestión de usuarios
- Reportes (solo para roles autorizados)
- Configuración (solo para Administradores)
- Perfil de usuario actual
- Botón de cerrar sesión

El sistema DEBE indicar visualmente la sección activa en el menú de navegación (highlighting).

**RUI-008: Ayuda contextual**

El sistema DEBE proporcionar ayuda contextual mediante iconos de ayuda (?) junto a campos o secciones que puedan requerir aclaración. Al hacer clic/hover sobre el icono, DEBE mostrarse un tooltip con explicación breve.

Para procesos complejos (ej: primer préstamo, registro de material nuevo), el sistema PUEDE proporcionar tour guiado opcional (walkthrough) para nuevos usuarios.

**RUI-009: Atajos de teclado**

El sistema DEBE soportar atajos de teclado para operaciones frecuentes:
- F2: Nueva búsqueda rápida
- F3: Nuevo préstamo
- F4: Nueva devolución
- Ctrl+G / Cmd+G: Ir a búsqueda global
- Esc: Cancelar operación actual / cerrar modal

El sistema DEBE mostrar una ventana de ayuda con todos los atajos disponibles cuando el usuario presione F1.

<!-- 
NOTA PARA ESTUDIANTES:
Pueden incluir MOCKUPS (bocetos de pantallas) en los Apéndices (Sección 4.3)
para complementar estos requisitos de interfaz. Los mockups son muy útiles pero
NO reemplazan los requisitos escritos.

Herramientas recomendadas para mockups:
- Figma (gratis para estudiantes)
- Balsamiq
- Draw.io
- Incluso papel y lápiz (escanear y adjuntar)
-->

[Complete con requisitos adicionales de interfaz de usuario según su proyecto]

<br>

#### 3.2.2 Interfaz de hardware

<!-- 
OBJETIVO:
Especificar características del hardware con el que el sistema interactuará
directamente, incluyendo dispositivos de entrada/salida, sensores, etc.

EJEMPLOS COMUNES:
- Lectores de código de barras
- Impresoras
- Dispositivos biométricos
- Cámaras
- Sensores
- Dispositivos de almacenamiento específicos

SI NO HAY INTERFACES DE HARDWARE:
Puede indicar explícitamente: "No aplica. El sistema no requiere interfaces con
hardware especializado más allá de computadoras estándar."
-->

**RHW-001: Lector de código de barras**

El sistema DEBE integrarse con lectores de código de barras USB compatibles con estándar HID (Human Interface Device). Específicamente, el sistema DEBE soportar el lector Zebra DS2208 que será utilizado en la biblioteca.

El lector de código de barras DEBE funcionar como entrada de teclado (modo emulación de teclado). Cuando se escanea un código de barras, el sistema DEBE recibir la secuencia de caracteres seguida de un Enter automático.

El sistema DEBE aceptar códigos de barras en los siguientes formatos:
- Code 39 (para carnets de biblioteca)
- Code 128 (para identificación de materiales)
- EAN-13 / ISBN (para libros comerciales)

El sistema DEBE validar que el código escaneado tenga formato válido antes de procesarlo. Si el código no es válido, DEBE mostrar mensaje de error y permitir reintentar el escaneo.

**RHW-002: Impresora térmica de tickets**

El sistema DEBE soportar impresión de comprobantes de préstamo en impresoras térmicas de 58mm o 80mm de ancho. El sistema DEBE generar tickets en formato ESC/POS compatible con la mayoría de impresoras térmicas.

Los comprobantes DEBEN incluir:
- Logo de la biblioteca (opcional, si la impresora soporta gráficos)
- Nombre de la biblioteca
- Número de carnet del usuario
- Nombre del usuario
- Lista de materiales prestados con código y título
- Fecha de préstamo
- Fecha de devolución
- Advertencia de multas por retraso
- Código QR opcional para consulta en línea

**RHW-003: Requisitos mínimos de hardware para estaciones de trabajo**

El sistema DEBE funcionar en computadoras con las siguientes especificaciones mínimas:
- Procesador: Intel Core i3 o AMD Ryzen 3 (o equivalente, mínimo dual-core 2.0 GHz)
- Memoria RAM: 4 GB mínimo, 8 GB recomendado
- Almacenamiento: 500 MB de espacio disponible (para cache del navegador)
- Pantalla: Resolución mínima 1024x768, recomendado 1366x768 o superior
- Conectividad: Puerto USB 2.0 o superior para lector de código de barras
- Red: Tarjeta de red Ethernet o WiFi para conexión a Internet

[Complete con otros requisitos de hardware si aplica a su proyecto]

<br>

#### 3.2.3 Interfaz de software

<!-- 
OBJETIVO:
Especificar cómo el sistema interactuará con otros sistemas de software,
incluyendo sistemas operativos, bases de datos, APIs externas, servicios web, etc.

INCLUIR:
- APIs de terceros que el sistema consumirá
- Servicios web que el sistema utilizará
- Integración con sistemas corporativos existentes
- Requisitos de bases de datos
- Bibliotecas o frameworks específicos (si son restricciones)

NIVEL DE DETALLE:
Suficiente para que los desarrolladores entiendan QUÉ integraciones son necesarias,
pero sin especificar excesivamente el CÓMO (eso va en diseño técnico).
-->

**RSW-001: Integración con Sistema Municipal de Identificación (SMI)**

El sistema DEBE integrarse con la API REST del Sistema Municipal de Identificación de Ciudadanos (SMI) versión 2.1 o superior.

**Endpoint a consumir**:
- URL: `https://api.municipalidad.gob/smi/v2/ciudadano/{tipo_documento}/{numero_documento}`
- Método: GET
- Autenticación: API Key en header `X-API-Key: [token]`

**Respuesta esperada** (JSON):
```json
{
  "valido": true,
  "datos": {
    "nombres": "Juan Carlos",
    "apellidos": "Pérez González",
    "fecha_nacimiento": "1990-05-15",
    "direccion": "Calle Principal 123"
  }
}
```

**Manejo de errores**:
- Timeout: 5 segundos máximo de espera
- Si la API retorna error 404: Documento no encontrado
- Si la API retorna error 500: Error del servidor externo
- Si no hay conectividad: Permitir operación sin validación

El sistema DEBE registrar todas las consultas a la API en el log del sistema para auditoría.

**RSW-002: Servidor de correo electrónico (SMTP)**

El sistema DEBE integrarse con el servidor SMTP institucional para envío de notificaciones por correo electrónico.

**Configuración SMTP**:
- Servidor: mail.municipalidad.gob
- Puerto: 587 (STARTTLS) o 465 (SSL/TLS)
- Autenticación: Usuario y contraseña proporcionados por IT de la municipalidad
- Remitente: biblioteca@municipalidad.gob

**Tipos de correos que el sistema enviará**:
- Bienvenida a nuevos usuarios
- Notificación de vencimiento de préstamo (7 días antes, 1 día antes, día del vencimiento)
- Notificación de préstamo vencido y multa generada
- Notificación de disponibilidad de material reservado
- Bloqueo de cuenta por intentos fallidos de login (RF-002)

Los correos DEBEN incluir:
- Logo de la biblioteca en el encabezado
- Contenido en HTML con fallback a texto plano
- Link para consultar detalles en el sistema (cuando aplique)
- Instrucciones claras de qué acción debe tomar el usuario
- Pie de página con información de contacto de la biblioteca

El sistema DEBE implementar cola de correos (queue) para no bloquear operaciones en caso de problemas con el servidor SMTP. Si un correo no se puede enviar, el sistema DEBE reintentar hasta 3 veces con intervalos de 5 minutos antes de marcarlo como "fallido".

**RSW-003: Base de datos PostgreSQL**

El sistema DEBE utilizar PostgreSQL versión 13 o superior como motor de base de datos.

**Requisitos de la base de datos**:
- Soporte de transacciones ACID
- Codificación UTF-8 para soporte de caracteres especiales
- Collation: es_ES.UTF-8 (o según localización)
- Timezone: Configurado según zona horaria local

El sistema DEBE crear esquema de base de datos con las siguientes características:
- Claves primarias en todas las tablas
- Claves foráneas con integridad referencial
- Índices en campos de búsqueda frecuente
- Constraints para validación de datos a nivel de BD
- Triggers para auditoría automática de cambios (opcional pero recomendado)

El sistema DEBE proporcionar scripts SQL para:
- Creación inicial del esquema
- Migración desde Excel (importación de datos legacy)
- Respaldo (backup) y restauración

**RSW-004: Servicios de respaldo (Backup)**

El sistema DEBE integrarse con el servicio de respaldo centralizado de la municipalidad mediante protocolo rsync o similar.

El sistema DEBE generar respaldos automáticos:
- **Respaldo completo**: Semanal (domingos a las 00:00)
- **Respaldo incremental**: Diario (cada día a las 00:00)
- **Respaldo de logs**: Diario (cada día a las 23:30)

Los respaldos DEBEN incluir:
- Dump completo de la base de datos
- Archivos de configuración del sistema
- Logs de auditoría
- Imágenes/documentos subidos al sistema (si los hay)

El sistema DEBE retener:
- Respaldos completos: Últimos 4 (4 semanas)
- Respaldos incrementales: Últimos 30 (30 días)
- Respaldos de logs: Últimos 90 días

El sistema DEBE notificar al administrador si un respaldo falla.

**RSW-005: Framework de desarrollo (Restricción técnica)**

[NOTA: Solo incluir esto si es una restricción REAL impuesta por el cliente o por estándares organizacionales. Normalmente, la elección de framework es decisión del equipo técnico y NO debe estar en requisitos, sino en diseño.]

Si el cliente/organización impone un framework específico, documentarlo así:

El sistema DEBE desarrollarse utilizando [Nombre del Framework] debido a estándares tecnológicos de la municipalidad. Todas las aplicaciones de la municipalidad usan este framework para facilitar mantenimiento futuro por el equipo interno de IT.

<!-- 
NOTA IMPORTANTE:
NO confunda requisitos de interfaz de software con decisiones de diseño técnico.

✓ CORRECTO (requisito):
"El sistema debe integrarse con el API de Sistema X para validar usuarios"

✗ INCORRECTO (decisión de diseño disfrazada de requisito):
"El sistema usará la biblioteca Axios para hacer llamadas HTTP"

La segunda es una decisión técnica que debe tomarse durante el diseño, no un requisito
del cliente (a menos que el cliente explícitamente lo exija por razones específicas).
-->

[Complete con otras integraciones de software relevantes para su proyecto]

<br>

#### 3.2.4 Interfaz de comunicación

<!-- 
OBJETIVO:
Especificar requisitos de comunicación en red, protocolos, seguridad de
comunicación, y requisitos de conectividad.

INCLUIR:
- Protocolos de red requeridos
- Requisitos de seguridad en comunicación
- Ancho de banda necesario
- Puertos de red
- Firewalls y configuraciones de red
- Cifrado de datos en tránsito
-->

**RCOM-001: Protocolo de comunicación web**

El sistema DEBE utilizar protocolo HTTPS (HTTP sobre TLS/SSL) para todas las comunicaciones entre navegador y servidor. El uso de HTTP sin cifrado NO DEBE ser permitido en producción.

El servidor DEBE configurarse con:
- Certificado SSL/TLS válido (no auto-firmado en producción)
- TLS versión 1.2 o superior
- Cipher suites modernos y seguros
- HTTP Strict Transport Security (HSTS) habilitado

Todas las páginas DEBEN forzar HTTPS. Si un usuario intenta acceder vía HTTP, DEBE ser redirigido automáticamente a HTTPS.

**RCOM-002: Requisitos de ancho de banda**

El sistema DEBE funcionar adecuadamente con la conexión a Internet existente de la biblioteca: 10 Mbps simétrica (download/upload).

El sistema DEBE optimizarse para uso eficiente del ancho de banda:
- Imágenes optimizadas y comprimidas
- Minificación de archivos CSS y JavaScript
- Uso de caché en navegador para recursos estáticos
- Compresión gzip/brotli para contenido textual

Con 10 Mbps, el sistema DEBE soportar al menos 15 usuarios simultáneos realizando operaciones normales sin degradación perceptible de rendimiento.

**RCOM-003: Puertos de red**

El sistema DEBE utilizar los siguientes puertos:

**Servidor Web**:
- Puerto 443 (HTTPS) - Acceso principal de usuarios
- Puerto 80 (HTTP) - Solo para redirigir a HTTPS

**Base de Datos** (acceso interno, no expuesto a Internet):
- Puerto 5432 (PostgreSQL) - Comunicación servidor web <-> BD

**SMTP** (salida):
- Puerto 587 (STARTTLS) o 465 (SSL/TLS) - Envío de correos

Todos los puertos DEBEN estar configurados en el firewall institucional. El equipo de IT de la municipalidad debe habilitar estos puertos antes del despliegue.

**RCOM-004: Seguridad en comunicación con APIs externas**

Todas las comunicaciones con APIs externas (Sistema Municipal de Identificación) DEBEN utilizar HTTPS.

Las API Keys o tokens de autenticación DEBEN:
- Almacenarse de forma segura (variables de entorno o vault, NO en código fuente)
- Transmitirse en headers HTTP, NUNCA en URL query parameters
- Tener fecha de expiración y mecanismo de renovación

El sistema DEBE implementar rate limiting para llamadas a APIs externas:
- Máximo 100 llamadas por minuto al SMI
- Implementar backoff exponencial si se reciben errores 429 (Too Many Requests)

**RCOM-005: Comunicación con impresora de red**

Si se utiliza impresora de red (no USB directa), el sistema DEBE comunicarse mediante:
- Protocolo: IPP (Internet Printing Protocol) o RAW TCP/IP
- Puerto: 631 (IPP) o 9100 (RAW)

La impresora DEBE estar en la misma red local que el servidor de aplicación para evitar problemas de latencia.

**RCOM-006: API REST del sistema (Requisito futuro)**

[En versión 1.0, el sistema NO expondrá API pública. Documentar como requisito futuro.]

En versiones futuras, el sistema PUEDE exponer una API REST pública para permitir integración con otras aplicaciones. Esta API deberá implementar:
- Autenticación mediante OAuth 2.0 o API Keys
- Versionamiento de API (v1, v2, etc.)
- Rate limiting por cliente
- Documentación OpenAPI/Swagger
- CORS configurado apropiadamente

Ver Sección 2.6 Requisitos Futuros.

[Complete con otros requisitos de comunicación específicos de su proyecto]

<br>

---

### 3.3 Requisitos no funcionales

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS NO FUNCIONALES
═══════════════════════════════════════════════════════════════════════════════

DEFINICIÓN:
Los requisitos no funcionales describen CÓMO debe comportarse el sistema, no QUÉ
debe hacer. Son atributos de calidad que el sistema debe poseer.

IMPORTANCIA CRÍTICA:
Los requisitos no funcionales son TAN IMPORTANTES como los funcionales, pero
frecuentemente se descuidan. Un sistema que hace todo lo que debe hacer (requisitos
funcionales) pero es lento, inseguro, o inestable, es un sistema FRACASADO.

CATEGORÍAS PRINCIPALES:
- Rendimiento (Performance)
- Fiabilidad (Reliability)
- Disponibilidad (Availability)
- Seguridad (Security)
- Mantenibilidad (Maintainability)
- Portabilidad (Portability)

PRINCIPIO FUNDAMENTAL:
Los requisitos no funcionales DEBEN ser CUANTIFICABLES y MEDIBLES.

✗ INCORRECTO: "El sistema será rápido"
✓ CORRECTO: "El sistema responderá a consultas en máximo 3 segundos en el 95% de los casos"

✗ INCORRECTO: "El sistema será seguro"
✓ CORRECTO: "El sistema cifrará todas las contraseñas usando bcrypt con factor de trabajo mínimo de 12"
-->

#### 3.3.1 Rendimiento

<!-- 
OBJETIVO:
Especificar requisitos de velocidad, tiempo de respuesta, throughput, capacidad,
y eficiencia de uso de recursos.

MÉTRICAS COMUNES:
- Tiempo de respuesta (response time)
- Throughput (transacciones por segundo)
- Utilización de recursos (CPU, memoria, disco, red)
- Capacidad (número de usuarios concurrentes, tamaño de base de datos)
-->

**RNFR-001: Tiempo de respuesta de interfaz web**

El sistema DEBE proporcionar tiempos de respuesta que garanticen una experiencia de usuario fluida:

- **Operaciones simples** (login, logout, navegación entre páginas): Máximo 1 segundo
- **Búsquedas en catálogo** (por título, autor, ISBN): Máximo 2 segundos
- **Operaciones de préstamo/devolución**: Máximo 3 segundos
- **Generación de reportes simples**: Máximo 5 segundos
- **Generación de reportes complejos**: Máximo 30 segundos
- **Importación masiva de datos**: Se permite mayor tiempo con indicador de progreso

Estos tiempos DEBEN cumplirse en el 95% de las operaciones (percentil 95) bajo condiciones normales de operación.

**Condiciones normales**: Hasta 15 usuarios concurrentes, base de datos con hasta 100,000 registros, servidor con carga CPU menor al 80%.

**RNFR-002: Capacidad de usuarios concurrentes**

El sistema DEBE soportar al menos 15 usuarios concurrentes simultáneos realizando operaciones sin degradación significativa de rendimiento (degradación <10% en tiempo de respuesta).

El sistema DEBE soportar hasta 50 usuarios concurrentes en momentos pico con degradación aceptable (<30% aumento en tiempo de respuesta).

**RNFR-003: Capacidad de almacenamiento de datos**

El sistema DEBE ser capaz de gestionar eficientemente:
- Hasta 100,000 registros de usuarios
- Hasta 50,000 materiales bibliográficos
- Hasta 500,000 registros de transacciones (préstamos/devoluciones) históricas
- Hasta 1,000,000 registros de auditoría

El rendimiento de búsquedas y operaciones NO DEBE degradarse significativamente cuando se alcancen estos volúmenes.

**RNFR-004: Utilización de recursos del servidor**

En condiciones normales de operación (15 usuarios concurrentes), el sistema NO DEBE exceder:
- 70% de uso de CPU
- 4 GB de uso de RAM
- 100 GB de almacenamiento en disco (incluyendo base de datos y logs)

El sistema DEBE liberar recursos apropiadamente (no memory leaks ni conexiones de BD sin cerrar).

**RNFR-005: Tamaño de página web**

Las páginas web del sistema (HTML + CSS + JS + imágenes) NO DEBEN exceder 2 MB de tamaño total por página para garantizar carga rápida incluso con conexiones lentas.

Recursos estáticos (CSS, JS, imágenes reutilizables) DEBEN configurarse con caché HTTP para evitar descargas repetidas.

**RNFR-006: Optimización de consultas a base de datos**

Las consultas SQL más frecuentes (búsqueda de usuarios, búsqueda de materiales, registro de préstamos) DEBEN completarse en menos de 100 milisegundos.

La base de datos DEBE tener índices apropiados en campos de búsqueda frecuente:
- Número de carnet de usuario
- ISBN o código de material
- Apellidos de usuario
- Título de material

<br>

#### 3.3.2 Fiabilidad

<!-- 
OBJETIVO:
Especificar requisitos sobre la capacidad del sistema de funcionar correctamente
bajo condiciones establecidas por un período de tiempo determinado.

MÉTRICAS COMUNES:
- MTBF (Mean Time Between Failures)
- MTTR (Mean Time To Repair)
- Tasa de errores aceptable
- Manejo de errores
- Recuperación ante fallos
-->

**RNFF-001: Tasa de fallos aceptable**

El sistema DEBE tener una tasa de fallos no superior a 1 fallo crítico por mes en promedio durante operación normal.

**Definición de fallo crítico**: Error que impide completamente el uso de una funcionalidad esencial (login, préstamos, devoluciones, búsqueda).

Errores menores (errores de validación, problemas de UI menores, features no esenciales) NO se consideran fallos críticos para este requisito.

**RNFF-002: Manejo robusto de errores**

El sistema DEBE manejar errores de forma elegante sin exponer al usuario a excepciones técnicas o pantallas en blanco:

- Errores de validación: Mostrar mensajes claros indicando qué corregir
- Errores de base de datos: Mostrar mensaje genérico y registrar error detallado en log
- Timeouts de APIs externas: Informar al usuario y ofrecer opción de reintentar
- Errores inesperados (500): Mostrar página de error amigable con opción de reportar el error

NINGÚN error DEBE exponer stack traces, queries SQL, o rutas del servidor al usuario.

**RNFF-003: Validación de datos**

El sistema DEBE validar TODOS los datos ingresados por usuarios tanto en cliente (JavaScript) como en servidor (backend) para prevenir datos corruptos o maliciosos:

- **Validación de formato**: Emails, fechas, números de documento, etc.
- **Validación de rangos**: Fechas futuras donde no aplica, números negativos donde no tiene sentido, etc.
- **Validación de integridad**: Claves foráneas válidas, relaciones consistentes
- **Sanitización**: Prevenir inyección SQL, XSS, etc.

Los datos rechazados DEBEN generar mensajes de error claros, NO simplemente fallar silenciosamente.

**RNFF-004: Integridad de transacciones**

Todas las operaciones críticas (préstamo, devolución, registro de usuario, modificación de catálogo) DEBEN ser transaccionales (ACID):

- **Atomicidad**: Si una operación falla, TODOS los cambios se revierten (rollback)
- **Consistencia**: Las reglas de negocio e integridad de BD se mantienen siempre
- **Aislamiento**: Operaciones concurrentes no interfieren entre sí
- **Durabilidad**: Operaciones completadas NO se pierden ante fallo del sistema

Ejemplo: Al registrar un préstamo, si se registra el préstamo pero falla el actualizar el estado del ejemplar, TODA la operación debe revertirse.

**RNFF-005: Recuperación ante errores de entrada**

Si un usuario ingresa datos incorrectos en un formulario largo (ej: registro de nuevo material bibliográfico con 20 campos), el sistema DEBE:
- Preservar todos los datos ya ingresados (no limpiar el formulario)
- Resaltar claramente los campos con error
- Permitir al usuario corregir solo los campos incorrectos sin reingresar todo

**RNFF-006: Logs detallados para diagnóstico**

El sistema DEBE registrar en logs:
- Todos los errores con timestamp, usuario afectado, y stack trace completo
- Advertencias (warnings) sobre situaciones anómalas
- Operaciones críticas completadas exitosamente
- Intentos de acceso no autorizado

Los logs DEBEN rotar diariamente y comprimirse después de 7 días. Los logs DEBEN retenerse por mínimo 90 días.

<br>

#### 3.3.3 Disponibilidad

<!-- 
OBJETIVO:
Especificar el porcentaje de tiempo que el sistema debe estar operativo y accesible.

MÉTRICAS COMUNES:
- Porcentaje de uptime (ej: 99.5%)
- Ventanas de mantenimiento permitidas
- Tiempo máximo de downtime
- Recuperación ante desastres
-->

**RNFD-001: Disponibilidad objetivo (Uptime)**

El sistema DEBE tener una disponibilidad mínima del 99.0% durante el horario de operación de la biblioteca (lunes a sábado, 8:00 AM a 8:00 PM).

**Cálculo**:
- Horario de operación: 12 horas/día × 6 días/semana = 72 horas/semana
- 99.0% uptime = Máximo 43 minutos de downtime no planificado por semana

Fuera del horario de operación, el sistema PUEDE estar inaccesible para mantenimiento sin afectar este SLA.

**RNFD-002: Ventanas de mantenimiento**

El sistema PUEDE tener downtime planificado para mantenimiento:
- **Mantenimiento regular**: Domingos de 00:00 a 06:00 (máximo 6 horas)
- **Actualizaciones mayores**: 2 veces por año, máximo 12 horas, con aviso de 1 semana de anticipación

El sistema DEBE mostrar página de mantenimiento informativa durante downtime planificado, indicando cuándo estará disponible nuevamente.

**RNFD-003: Monitoreo de disponibilidad**

El sistema DEBE implementar monitoreo automático de disponibilidad (health check):
- Endpoint: /health o /status
- Verificación cada 1 minuto
- Si el sistema no responde en 3 verificaciones consecutivas (3 minutos), se considera "down"

Si el sistema queda "down", DEBE enviarse notificación automática al administrador del sistema y al equipo de soporte de IT.

**RNFD-004: Recuperación ante fallo**

En caso de fallo del servidor principal, el sistema DEBE poder restablecerse en máximo 4 horas utilizando respaldos automáticos (ver RSW-004).

El proceso de recuperación DEBE estar documentado en un manual de operaciones con pasos claros para:
1. Identificar la causa del fallo
2. Decidir entre reparación vs. restauración desde backup
3. Ejecutar restauración desde último backup disponible
4. Verificar integridad de datos restaurados
5. Reiniciar servicio

[OPCIONAL: Si el presupuesto lo permite, especificar servidor de respaldo activo-pasivo para failover automático, pero esto puede estar fuera del alcance de proyectos pequeños]

**RNFD-005: Degradación controlada**

Si servicios externos (Sistema Municipal, servidor SMTP) no están disponibles, el sistema DEBE continuar operando con funcionalidad reducida en lugar de fallar completamente:

- Si SMI no está disponible: Permitir registro manual sin validación automática
- Si SMTP no está disponible: Encolar correos para envío posterior

El sistema DEBE informar al usuario cuando opera en "modo degradado" sin alarmar innecesariamente.

<br>

#### 3.3.4 Seguridad

<!-- 
OBJETIVO:
Especificar requisitos para proteger el sistema contra accesos no autorizados,
garantizar confidencialidad, integridad, y disponibilidad de la información (CIA Triad).

CATEGORÍAS:
- Autenticación
- Autorización
- Auditoría
- Confidencialidad
- Integridad de datos
- Protección contra ataques comunes
-->

**RNFS-001: Almacenamiento seguro de contraseñas**

El sistema NUNCA DEBE almacenar contraseñas en texto plano. Las contraseñas DEBEN almacenarse usando algoritmo de hashing fuerte:
- Algoritmo: bcrypt, scrypt, o Argon2
- Factor de trabajo (cost): Mínimo 12 para bcrypt
- Cada contraseña DEBE tener sal (salt) única generada aleatoriamente

El sistema NUNCA DEBE permitir recuperación de contraseñas (NO "enviar contraseña"), solo restablecimiento mediante token temporal.

**RNFS-002: Política de contraseñas**

El sistema DEBE aplicar política de contraseñas seguras:

**Para usuarios del sistema (bibliotecarios, administradores)**:
- Longitud mínima: 8 caracteres
- DEBE contener al menos: 1 mayúscula, 1 minúscula, 1 número, 1 carácter especial
- NO DEBE ser contraseña común (comparar contra lista de passwords comprometidos)
- DEBE cambiarse cada 90 días
- NO DEBE reutilizarse las últimas 5 contraseñas

**Para usuarios finales (clientes biblioteca)**: Política más relajada
- Longitud mínima: 6 caracteres
- Al menos 1 letra y 1 número

**RNFS-003: Cifrado de comunicaciones**

El sistema DEBE cifrar TODA comunicación sensible:
- HTTPS (TLS 1.2+) para todas las páginas web - Sin excepciones
- Conexiones a base de datos cifradas (si BD está en servidor separado)
- Tokens de API y credenciales transmitidas en headers cifrados, NUNCA en URL

**RNFS-004: Protección contra ataques comunes**

El sistema DEBE implementar protecciones contra vectores de ataque comunes:

**SQL Injection**:
- Usar prepared statements o ORMs
- NUNCA concatenar strings para construir queries SQL

**Cross-Site Scripting (XSS)**:
- Sanitizar TODAS las entradas de usuario antes de renderizar en HTML
- Usar Content Security Policy (CSP) headers

**Cross-Site Request Forgery (CSRF)**:
- Implementar tokens CSRF en todos los formularios
- Validar tokens en el servidor

**Clickjacking**:
- Usar X-Frame-Options: DENY o SAMEORIGIN header

**Brute Force**:
- Implementar bloqueo de cuenta después de intentos fallidos (ver RF-002)
- Implementar CAPTCHA después de 3 intentos fallidos (opcional)

**RNFS-005: Autorización y control de acceso**

El sistema DEBE verificar permisos en CADA operación, no solo en la UI:
- Verificación en backend, no confiar en controles de UI
- Principio de menor privilegio: usuarios solo acceden a lo estrictamente necesario
- Denegación por defecto: lo que no está explícitamente permitido, está prohibido

El sistema DEBE prevenir escalamiento de privilegios: un usuario con rol Bibliotecario NO DEBE poder ejecutar operaciones de Administrador aunque intente manipular requests HTTP.

**RNFS-006: Auditoría de seguridad**

El sistema DEBE registrar eventos de seguridad:
- Todos los logins exitosos y fallidos
- Cambios de contraseña
- Cambios de permisos de usuario
- Accesos a datos sensibles (historial de préstamos de usuarios)
- Intentos de acceso no autorizado
- Modificaciones a configuración del sistema

Los registros de auditoría DEBEN incluir: timestamp, usuario, dirección IP, acción, recurso afectado, resultado (éxito/fallo).

Los logs de auditoría DEBEN ser inmutables (append-only) y almacenarse de forma segura.

**RNFS-007: Gestión de sesiones**

Las sesiones de usuario DEBEN ser seguras:
- IDs de sesión generados criptográficamente aleatorios (mínimo 128 bits)
- Sesiones almacenadas en servidor, NO en cookies del cliente (excepto session ID)
- Timeout de inactividad: 30 minutos
- Sesión invalidada completamente al hacer logout
- Protección contra session fixation: regenerar session ID después de login exitoso

**RNFS-008: Protección de datos personales (GDPR/LOPD)**

El sistema DEBE cumplir con regulaciones de protección de datos:
- Almacenar solo datos personales estrictamente necesarios
- Permitir a usuarios solicitar eliminación de sus datos (derecho al olvido)
- Permitir a usuarios exportar sus datos (portabilidad de datos)
- Obtener consentimiento explícito para procesamiento de datos (al registrarse)
- Notificar a usuarios sobre brechas de seguridad que afecten sus datos

Los datos sensibles (historial de préstamos, datos personales) NO DEBEN ser accesibles por personal no autorizado.

**RNFS-009: Respaldos seguros**

Los respaldos de la base de datos DEBEN estar cifrados. Las claves de cifrado NO DEBEN almacenarse en el mismo servidor que los respaldos.

<br>

#### 3.3.5 Mantenibilidad

<!-- 
OBJETIVO:
Especificar qué tan fácil debe ser mantener, modificar, y extender el sistema.

ASPECTOS:
- Documentación del código
- Estructura modular
- Facilidad de diagnóstico de problemas
- Facilidad de actualización
-->

**RNFM-001: Documentación del código**

El código fuente DEBE estar documentado de forma que futuros desarrolladores puedan entenderlo y modificarlo:

- Funciones y métodos complejos DEBEN tener comentarios explicando QUÉ hacen y POR QUÉ (no solo CÓMO)
- Clases y módulos DEBEN tener docstrings/javadocs describiendo su propósito
- README principal DEBE explicar cómo instalar, configurar, y ejecutar el proyecto
- README DEBE incluir instrucciones para ambiente de desarrollo local

**RNFM-002: Código limpio y estándares**

El código DEBE seguir estándares de codificación reconocidos:
- Nombres de variables, funciones, y clases descriptivos (no abreviaciones crípticas)
- Funciones pequeñas con responsabilidad única (idealmente <50 líneas)
- DRY (Don't Repeat Yourself): evitar código duplicado
- Seguir guías de estilo del lenguaje (PEP8 para Python, PSR para PHP, etc.)

El proyecto DEBE incluir linter configurado para verificar cumplimiento de estándares.

**RNFM-003: Modularidad**

El sistema DEBE estructurarse en módulos independientes con responsabilidades claras:
- Separación entre lógica de negocio, acceso a datos, y presentación (MVC o similar)
- Bajo acoplamiento entre módulos
- Alta cohesión dentro de módulos

Modificaciones en un módulo NO DEBEN requerir cambios en múltiples otros módulos (excepto casos justificados).

**RNFM-004: Facilidad de configuración**

Parámetros configurables del sistema (URLs de APIs, credenciales de BD, timeouts, límites, etc.) NO DEBEN estar hardcodeados en el código fuente.

La configuración DEBE externalizarse en:
- Archivo de configuración (config.ini, .env, etc.)
- Variables de entorno
- Base de datos de configuración (para parámetros modificables desde UI de administración)

Cambios de configuración NO DEBEN requerir recompilación o modificación de código.

**RNFM-005: Logs para diagnóstico**

El sistema DEBE generar logs suficientemente detallados para diagnosticar problemas:
- Niveles de log apropiados: DEBUG, INFO, WARNING, ERROR, CRITICAL
- En producción: nivel INFO o WARNING como mínimo
- En desarrollo: nivel DEBUG disponible
- Logs DEBEN incluir contexto: usuario, operación intentada, datos relevantes (sin exponer información sensible)

**RNFM-006: Manejo de dependencias**

El proyecto DEBE documentar claramente todas las dependencias externas:
- Archivo requirements.txt (Python), package.json (Node.js), composer.json (PHP), etc.
- Versiones específicas o rangos de versiones compatibles
- Instrucciones para instalar dependencias

Actualizaciones de dependencias DEBEN probarse en ambiente de staging antes de producción.

<br>

#### 3.3.6 Portabilidad

<!-- 
OBJETIVO:
Especificar qué tan fácil es transferir el sistema a diferentes entornos o plataformas.

ASPECTOS:
- Independencia de plataforma
- Facilidad de migración
- Compatibilidad
-->

**RNFP-001: Independencia de sistema operativo del servidor**

El sistema DEBE poder ejecutarse en servidores Linux (Ubuntu 20.04+, Debian 10+, CentOS 8+) sin modificaciones.

El sistema PUEDE ser compatible con otros sistemas operativos (Windows Server, macOS) pero esto NO es un requisito esencial.

**RNFP-002: Compatibilidad de base de datos**

Aunque el sistema usará PostgreSQL en producción (ver restricción RSW-003), el código DEBE estructurarse de forma que migrar a otro RDBMS (MySQL, MariaDB) requiera cambios mínimos.

Esto se logra usando:
- ORM (Object-Relational Mapping) que abstrae el motor de BD
- Evitar queries SQL específicas de PostgreSQL (a menos que sean críticas para rendimiento)

**RNFP-003: Contenedorización (Deseable)**

[Este es un requisito DESEABLE, no esencial para v1.0]

El sistema DEBERÍA poder empaquetarse en contenedores Docker para facilitar despliegue en diferentes entornos:
- Dockerfile para construir imagen del sistema
- docker-compose.yml para orquestar contenedores (app, BD, nginx)

Esto facilitaría:
- Despliegue consistente en desarrollo, staging, y producción
- Migración futura a servicios cloud (AWS, Azure, GCP)
- Escalabilidad horizontal (múltiples instancias)

**RNFP-004: Independencia de ruta de instalación**

El sistema NO DEBE asumir rutas fijas del sistema de archivos hardcodeadas. Las rutas DEBEN ser configurables o relativas a la ubicación de instalación.

Esto permite instalar el sistema en diferentes directorios según las políticas de cada organización.

**RNFP-005: Exportación de datos**

El sistema DEBE permitir exportar datos en formatos estándar para facilitar migración futura:
- Exportación de catálogo de materiales: CSV, JSON, MARCXML
- Exportación de usuarios: CSV, JSON
- Exportación de transacciones: CSV, JSON

Esto garantiza que los datos NO quedan "atrapados" en el sistema.

---

### 3.4 Requisitos de diseño

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS DE DISEÑO
═══════════════════════════════════════════════════════════════════════════════

OBJETIVO:
Especificar restricciones o decisiones de diseño que deben seguirse por razones
específicas (regulatorias, estándares organizacionales, compatibilidad, etc.).

NOTA IMPORTANTE:
Esta sección es OPCIONAL y debe usarse con cuidado. En general, se debe dar
libertad al equipo de diseño para tomar decisiones técnicas. Solo incluir aquí
decisiones de diseño que son IMPUESTAS por requisitos externos no negociables.

DIFERENCIA CLAVE:
- Restricción legítima: "El sistema debe seguir el manual de identidad visual de la municipalidad"
- Micro-gestión técnica: "El sistema debe usar patrón MVC con controladores en carpeta /app/controllers"

La segunda es una decisión técnica que debe quedar en manos del equipo de desarrollo,
a menos que haya una razón de negocio FUERTE para especificarla.
-->

**RD-001: Estándares de interfaz de usuario**

El diseño de la interfaz de usuario DEBE seguir el Manual de Identidad Visual de la Municipalidad disponible en [URL o referencia]:

- Paleta de colores: Usar colores oficiales de la municipalidad
  - Primario: #004B87 (azul institucional)
  - Secundario: #FFB81C (amarillo institucional)
  - Textos: #333333
  - Fondos: #FFFFFF, #F5F5F5

- Tipografía: Usar fuentes oficiales
  - Encabezados: Montserrat Bold
  - Cuerpo de texto: Open Sans Regular

- Logo: Incluir logo oficial de la municipalidad en header de todas las páginas

**RD-002: Formato de reportes**

Los reportes generados por el sistema DEBEN seguir el formato estándar de documentos de la biblioteca:
- Header con logo y nombre de la biblioteca
- Pie de página con dirección, teléfono, y sitio web
- Formato PDF con metadatos adecuados (título, autor, fecha de creación)

**RD-003: Nomenclatura de identificadores**

El sistema DEBE seguir las siguientes convenciones de nomenclatura establecidas por la biblioteca:

- **Carnets de usuarios**: Formato "BMUN-XXXXXX" donde XXXXXX es número consecutivo
- **Código de materiales**: 
  - Libros: ISBN-13 cuando disponible
  - Otros materiales: "MAT-XXXXXX" número consecutivo
- **Números de préstamo**: Formato "PREST-AAAA-XXXXXX" donde AAAA es año y XXXXXX consecutivo del año

[Si NO hay restricciones específicas de diseño impuestas externamente, puede indicarlo explícitamente]

**Nota**: Además de los requisitos anteriores, las decisiones de arquitectura y diseño técnico del sistema (patrones de diseño, estructura de base de datos, organización de código, etc.) quedan a criterio del equipo de desarrollo, siempre que cumplan con todos los requisitos funcionales y no funcionales especificados en este documento.

<br>

---

### 3.5 Requisitos de calidad

<!-- 
═══════════════════════════════════════════════════════════════════════════════
REQUISITOS DE CALIDAD
═══════════════════════════════════════════════════════════════════════════════

OBJETIVO:
Especificar estándares de calidad que el sistema y el proceso de desarrollo deben cumplir.

NOTA: Algunos de estos requisitos pueden solaparse con requisitos no funcionales.
La diferencia es que aquí especificamos procesos y prácticas de calidad, mientras
que en RNF especificamos atributos del sistema final.
-->

**RC-001: Cobertura de pruebas**

El sistema DEBE tener pruebas automatizadas con cobertura mínima de:
- **Pruebas unitarias**: 70% de cobertura del código
- **Pruebas de integración**: Todas las integraciones críticas (SMI, SMTP, BD)
- **Pruebas de interfaz (E2E)**: Flujos de usuario principales (login, préstamo, devolución, búsqueda)

Las pruebas DEBEN ejecutarse automáticamente antes de cada despliegue. Un despliegue NO DEBE realizarse si las pruebas fallan.

**RC-002: Revisión de código**

Todo código antes de fusionarse a la rama principal (main/master) DEBE pasar por:
- Revisión por al menos un desarrollador adicional (peer review)
- Aprobación explícita del revisor
- Pasar todas las pruebas automatizadas
- Cumplir con los estándares de código (verificado por linter)

**RC-003: Control de versiones**

El proyecto DEBE usar sistema de control de versiones (Git) con las siguientes prácticas:
- Commits frecuentes con mensajes descriptivos
- Rama main/master siempre en estado desplegable (no romper main)
- Feature branches para desarrollo de nuevas funcionalidades
- Tags para versiones de producción (v1.0, v1.1, etc.)

**RC-004: Ambiente de staging**

El sistema DEBE probarse en ambiente de staging (idéntico a producción) antes de cada despliegue a producción. Los despliegues a producción SOLO se realizan si las pruebas en staging son exitosas.

**RC-005: Plan de pruebas**

El equipo DEBE crear un Plan de Pruebas documentado que especifique:
- Casos de prueba para cada requisito funcional
- Estrategia de pruebas (unitarias, integración, sistema, aceptación)
- Criterios de aceptación
- Responsables de ejecutar pruebas

<br>

---

### 3.6 Restricciones del sistema

<!-- 
Esta sección puede usarse para enumerar restricciones adicionales no cubiertas
en secciones previas, o puede referenciarse a la Sección 2.4 si todas las
restricciones ya fueron documentadas allí.
-->

Ver Sección 2.4 para restricciones completas del sistema. Las restricciones principales son:

- Restricciones tecnológicas: Servidores Linux existentes, PostgreSQL como BD
- Restricciones de integración: API del Sistema Municipal de Identificación v2.1
- Restricciones presupuestarias: Máximo $25,000 USD
- Restricciones de tiempo: Implementación en 6 meses
- Restricciones de personal: Equipo de 4 personas
- Restricciones regulatorias: Cumplimiento de Ley de Protección de Datos Personales

[O puede expandir con restricciones adicionales no mencionadas en 2.4]

<br>

---

### 3.7 Atributos del sistema

<!-- 
Esta sección puede usarse para especificar atributos adicionales del sistema
no cubiertos en otras secciones, o puede omitirse si todo ya está documentado.

Ejemplos de atributos adicionales:
- Estándares de documentación
- Procesos de entrega
- Capacitación requerida
- Garantías y soporte post-implementación
-->

**A-001: Documentación de usuario**

El sistema DEBE incluir:
- **Manual de Usuario Final** (para clientes de biblioteca que usen catálogo en línea): Mínimo 10 páginas, con capturas de pantalla
- **Manual de Usuario del Sistema** (para bibliotecarios): Mínimo 30 páginas, con procedimientos paso a paso para todas las operaciones
- **Manual de Administrador**: Mínimo 20 páginas, incluyendo configuración, respaldos, solución de problemas
- **Ayuda en línea**: Documentación contextual accesible desde la interfaz del sistema

Toda la documentación DEBE estar en español y en formato PDF.

**A-002: Capacitación del personal**

El proveedor del sistema DEBE proporcionar capacitación al personal de la biblioteca:
- **Capacitación para bibliotecarios**: 2 sesiones de 4 horas (total 8 horas)
  - Sesión 1: Operaciones diarias (préstamos, devoluciones, búsqueda)
  - Sesión 2: Gestión de usuarios, reportes básicos
  
- **Capacitación para administradores**: 2 sesiones de 4 horas (total 8 horas)
  - Sesión 1: Configuración del sistema, gestión de catálogo
  - Sesión 2: Respaldos, solución de problemas, reportes avanzados

La capacitación DEBE incluir material impreso y ejercicios prácticos. DEBE realizarse en las instalaciones de la biblioteca.

**A-003: Período de garantía**

El sistema DEBE incluir garantía de 12 meses desde la fecha de aceptación en producción, que incluye:
- Corrección de errores (bugs) sin costo adicional
- Soporte técnico vía email con tiempo de respuesta máximo de 48 horas laborales
- Actualizaciones de seguridad sin costo

Después del período de garantía, se establecerá contrato de mantenimiento separado (fuera del alcance de este SRS).

**A-004: Migración de datos**

El proveedor DEBE realizar la migración de datos desde el sistema actual (Excel) al nuevo sistema, incluyendo:
- Importación de catálogo de materiales (~25,000 registros)
- Importación de usuarios (~15,000 registros)
- Validación de integridad de datos migrados
- Generación de reporte de migración con estadísticas y problemas encontrados

La migración DEBE realizarse en coordinación con el personal de la biblioteca para resolver inconsistencias en datos legacy.

**A-005: Criterios de aceptación del sistema**

El sistema se considerará aceptado cuando:
1. Todos los requisitos funcionales esenciales estén implementados y probados
2. Todos los requisitos no funcionales esenciales se cumplan
3. La migración de datos se haya completado exitosamente
4. La capacitación del personal se haya completado
5. El sistema haya operado en producción por 2 semanas sin errores críticos
6. El cliente firme documento de aceptación formal

<br>

---

## 4 APÉNDICES

<!-- 
═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 4: APÉNDICES
═══════════════════════════════════════════════════════════════════════════════

PROPÓSITO:
Los apéndices contienen información complementaria que respalda y aclara las
secciones anteriores, pero que por su extensión o naturaleza se documenta mejor
por separado.

CONTENIDO TÍPICO:
- Modelos de casos de uso
- Diagramas del sistema
- Prototipos de interfaces
- Esquemas de base de datos
- Matrices de trazabilidad
- Glosario extendido
- Análisis de requisitos
- Criterios de evaluación

NOTA IMPORTANTE:
Los apéndices NO son opcionales si contienen información crítica para entender
los requisitos. Son parte integral del SRS.
-->

### 4.1 Modelos de casos de uso

<!-- 
Los casos de uso describen interacciones completas entre actores y el sistema
para lograr un objetivo específico. Complementan los requisitos funcionales
proporcionando contexto y flujos de trabajo.
-->

**Lista de Casos de Uso del Sistema:**

- **CU-001**: Realizar Préstamo de Material (documentado arriba)
- 
- **CU-002**: Realizar Devolución de Material
- **CU-003**: Registrar Nuevo Usuario
- **CU-004**: Buscar Material en Catálogo
- **CU-005**: Crear Reserva de Material
- **CU-006**: Renovar Préstamo
- **CU-007**: Procesar Pago de Multa
- **CU-008**: Generar Reporte de Materiales Más Prestados
- **CU-009**: Configurar Parámetros del Sistema
- **CU-010**: Realizar Respaldo de Datos
- ... [continuar según necesidad]
<br>

<!--
ESTRUCTURA DE UN CASO DE USO:

**Plantilla de Caso de Uso:**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-001 |
| **Nombre** | [Nombre descriptivo del caso de uso] |
| **Actores** | [Quién interactúa: Usuario, Bibliotecario, Sistema externo, etc.] |
| **Descripción** | [Breve descripción del objetivo del caso de uso] |
| **Precondiciones** | [Estado que debe existir antes de ejecutar el caso de uso] |
| **Postcondiciones** | [Estado después de ejecutar exitosamente el caso de uso] |
| **Flujo Principal** | 1. [Paso 1]<br>2. [Paso 2]<br>3. [Paso 3]<br>... |
| **Flujos Alternativos** | **2a**. Si [condición]:<br>  2a1. [Paso alternativo]<br>  2a2. [Volver al paso X] |
| **Flujos de Excepción** | **3a**. Si [error]:<br>  3a1. [Manejo del error]<br>  3a2. [Fin del caso de uso o recuperación] |
| **Requisitos Relacionados** | [RF-XXX, RF-YYY] |

**Punto 6**
-->

**CU-001: Resturante unicafe**

| Campo | Descripción |
|-------|-------------|
| *ID* | CU-001 |
| *Nombre* | mirar menu|
| *Actores* | chef (primario), Usuario del restaurante (secundario) |
| *Descripción* | permite al usuario visualizar el menú semanal, para posteriormente realizar tareas como hacer pedido|
| *Precondiciones* | 1. Al usuario se le válido el carnet<br>2. El usuario NO está suspendido ni tiene multas |
| *Postcondiciones* | 1. La página debe redirigir al usuario a una nueva pagina<br>2. la nueva página debe contener el menú semanal  |
| *Flujo Principal* | 1. El sistema solicita identificarse,mediante un carnet<br>2. El usuario escanea su carnet <br>3. el sistema valida el carnet<br>4. El usuario escanea el código QR<br>5. El sistema redirige al usuario a una nueva pestańa <br>6. El usuario visualiza el menú semanal<br>7. El usuario hace su pedido |
| *Flujos Alternativos* | *4a. carnet no valido:<br>  4a1. El sistema muestra mensaje "carted invalido"<br>  4a2. El sistema ofrece opción "llamar su soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br>7a. error en la pagina*:<br>  7a1.  El sistema nuestra un mensaje "error"<br>  7a2. Si esto sucede, el sistema ofrece opción "reportar problema"<br>  7a3. un usuario de soporte será alertado <bro> 7a4. se soluciona el problema |
| *Flujos de Excepción* | *5a. Usuario suspendido o con multas vencidas*:<br>  5a1. El sistema muestra advertencia "Usuario suspendido" o "Usuario tiene multas vencidas por $[monto]"<br>  5a2. El sistema NO permite continuar con la venta<br>  5a3. Fin del caso de uso<br>  |
| *Requisitos Relacionados* | CU-01 (visualizar menu)<br>CU-02 (Escanear QR)<br>CU-03 (consulta menú semanal) |
<br>

<!--
sobre LOS SUBCASOS DE USO:

Un **subcaso de uso** es un caso de uso que:
1. **NO puede ejecutarse de forma independiente**
2. **Siempre es invocado por otro caso de uso** (relación <<include>>)
3. **Representa funcionalidad compartida** por múltiples casos de uso
4. **Es un fragmento funcional** del sistema, no un proceso completo

Documenta un subcaso de uso cuando:
1. Es INCLUIDO (<<include>>) por 2+ casos de uso, Y
2. Tiene complejidad suficiente que merece especificación separada

**Ejemplos:**
- Validar Credenciales de Usuario (usado en Login, Cambiar Contraseña, Desbloquear Cuenta)
- Calcular Costo Total con Impuestos (usado en Ver Carrito, Generar Factura, Procesar Pago)
- Verificar Disponibilidad de Inventario (usado en Agregar a Carrito, Crear Pedido, Reservar)


NO documentes un subcaso cuando:
- Es usado por un solo CU (documéntalo como parte del CU principal)
- Es trivial (1-2 pasos simples)

**Ejemplos de NO subcasos:**
- Cerrar Sesión (trivial: 1 paso)
- Guardar Log (técnico, no lógica de negocio)
- Actualizar Timestamp (trivial)
- Formatear Fecha para Mostrar (técnico)

¿CÓMO DOCUMENTAR UN SUBCASO DE USO?

opcion 1: **Plantilla de Subcaso de Uso:**

| **Campo**                   | **Descripción**                                                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **ID**                      | CU-XXX.Y (donde XXX es el CU padre y Y es el número de subcaso)                                                                      |
| **Nombre**                  | [Nombre descriptivo del subcaso]                                                                                                     |
| **Tipo**                    | Subcaso de uso (<> del caso padre)                                                                                                   |
| **Usado por**               | CU-AAA, CU-BBB, CU-CCC (casos de uso que lo invocan)                                                                                 |
| **Descripción**             | [Descripción del propósito del subcaso y su relación con el CU padre]                                                                |
| **Precondiciones**          | [Estado que debe existir antes de ejecutar este subcaso]                                                                             |
| **Postcondiciones**         | [Estado resultante después de ejecutar este subcaso]                                                                                 |
| **Entradas**                | [Datos o parámetros que recibe del caso de uso padre]                                                                                |
| **Salidas**                 | [Datos o resultados que devuelve al caso de uso padre]                                                                               |
| **Flujo Principal**         | 1. [Paso 1]<br>2. [Paso 2]<br>3. [Paso 3]<br>...                                                                                     |
| **Flujos Alternativos**     | **2a**. Si [condición]:<br>  2a1. [Paso alternativo]<br>  2a2. [Retornar al paso X del flujo principal]                              |
| **Excepciones**             | **3a**. Si [error o evento inesperado]:<br>  3a1. [Acción de manejo o notificación]<br>  3a2. [Fin del subcaso o retorno controlado] |
| **Reglas de Negocio**       | [RB-XXX, RB-YYY, u otras reglas que aplican]                                                                                         |
| **Requisitos Relacionados** | [RF-XXX, RF-YYY]                                                                                                                     |
<br>
-->

| **Campo**                                | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ID**                                   | **CU-VAL-001**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Nombre**                               | Validar Credenciales de Usuario                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Tipo**                                 | Subcaso de uso (<<include>>)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Usado por**                            | • CU-001: Login al Sistema<br>• CU-025: Cambiar Contraseña<br>• CU-030: Desbloquear Cuenta<br>• CU-045: Autorizar Operación Crítica                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Descripción**                          | Valida que las credenciales proporcionadas (usuario + contraseña) son correctas y que la cuenta está en condiciones de ser utilizada. Verifica contra la base de datos de usuarios, valida el hash de la contraseña y comprueba el estado de la cuenta. Este subcaso encapsula toda la lógica de autenticación para garantizar consistencia en todo el sistema.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Precondiciones**                       | 1. El sistema está conectado a la base de datos de usuarios.<br>2. Los datos de entrada (usuario y contraseña) no son nulos ni vacíos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Postcondiciones (Éxito)**              | 1. Las credenciales son válidas.<br>2. Se registra intento exitoso en log de auditoría.<br>3. Se actualiza fecha/hora de último acceso del usuario.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Postcondiciones (Fallo)**              | 1. Las credenciales NO son válidas (usuario no existe o contraseña incorrecta).<br>2. Se registra intento fallido en log de auditoría.<br>3. Se incrementa contador de intentos fallidos.<br>4. Si contador alcanza 5 → Se bloquea cuenta temporalmente (30 min).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Entradas**                             | **nombre_usuario** *(String)*: Nombre de usuario o email (**Obligatorio**).<br>**contraseña** *(String)*: Contraseña en texto plano (**Obligatorio**).<br>**ip_origen** *(String)*: Dirección IP del cliente (Opcional, para auditoría).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Salidas**                              | **resultado** *(Boolean)*: TRUE si credenciales válidas, FALSE si inválidas.<br>**motivo_fallo** *(String)*: Si resultado=FALSE → “usuario_no_existe” / “contraseña_incorrecta” / “cuenta_bloqueada”.<br>**usuario_id** *(Integer)*: Si resultado=TRUE → ID del usuario autenticado.<br>**datos_usuario** *(Object)*: Si resultado=TRUE → Objeto con nombre, rol y permisos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Flujo Principal**                      | 1. Recibir parámetros de entrada (nombre_usuario, contraseña, ip_origen).<br>2. Buscar usuario en base de datos por nombre_usuario.<br>3. Si usuario no encontrado → Ir a Excepción 3a.<br>4. Verificar hash de contraseña:<br> • Obtener hash almacenado y salt.<br> • Calcular hash de contraseña proporcionada.<br> • Comparar hashes.<br>5. Si hashes no coinciden → Ir a Excepción 5a.<br>6. Verificar estado de cuenta:<br> • estado = “activo”<br> • intentos_fallidos < 5<br> • bloqueo_hasta IS NULL o < AHORA().<br>7. Si cuenta bloqueada o inactiva → Ir a Excepción 7a.<br>8. **Credenciales válidas:** Resetear intentos_fallidos = 0; actualizar fecha e IP último acceso.<br>9. Registrar en log de auditoría (“login_exitoso”).<br>10. Retornar resultado=TRUE, usuario_id, datos_usuario.<br>11. **Fin del Subcaso – Éxito.** |
| **Flujos Alternativos**                  | **Ninguno** (todos los caminos no exitosos se manejan como excepciones).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Flujos de Excepción**                  | **3a – Usuario no encontrado:**<br>1. Registrar en log “intento_login_usuario_inexistente”.<br>2. No revelar si el usuario existe o no (seguridad).<br>3. Retornar resultado=FALSE, motivo_fallo="credenciales_invalidas".<br>4. **Fin – Fallo.**<br><br>**5a – Contraseña incorrecta:**<br>1. Incrementar intentos_fallidos.<br>2. Si >=5, bloquear cuenta 30 min y notificar por email.<br>3. Registrar en log “intento_login_contraseña_incorrecta”.<br>4. Retornar resultado=FALSE, motivo_fallo="credenciales_invalidas".<br>5. **Fin – Fallo.**<br><br>**7a – Cuenta bloqueada o inactiva:**<br>1. Determinar motivo: “cuenta_inactiva”, “bloqueada_temporalmente” o “bloqueada_por_seguridad”.<br>2. Registrar en log.<br>3. Retornar resultado=FALSE, motivo_fallo=[motivo].<br>4. **Fin – Fallo.**                                     |
| **Reglas de Negocio**                    | **RN-SEC-001:** Las contraseñas NUNCA se almacenan en texto plano (usar bcrypt cost=12).<br>**RN-SEC-002:** Después de 5 intentos fallidos, la cuenta se bloquea por 30 minutos.<br>**RN-SEC-003:** Los mensajes de error no deben revelar si el usuario existe o no.<br>**RN-SEC-004:** Todos los intentos (éxito/fallo) se registran en log de auditoría.<br>**RN-SEC-005:** El bloqueo temporal se resetea automáticamente después de 30 min.                                                                                                                                                                                                                                                                                                                                                                                                |
| **Requisitos No Funcionales Aplicables** | **RNFS-001:** Almacenamiento seguro de contraseñas (bcrypt).<br>**RNFS-002:** Protección contra fuerza bruta (bloqueo tras 5 intentos).<br>**RNFR-001:** Tiempo de respuesta < 500 ms.<br>**RNFS-006:** Auditoría de seguridad (registro completo de intentos).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| **Casos de Prueba del Subcaso**          | **TC-VAL-001:** Credenciales válidas → resultado=TRUE, usuario_id retornado.<br>**TC-VAL-002:** Usuario no existe → resultado=FALSE, motivo="credenciales_invalidas".<br>**TC-VAL-003:** Contraseña incorrecta → resultado=FALSE, intentos_fallidos++.<br>**TC-VAL-004:** 5to intento fallido → cuenta bloqueada 30 min.<br>**TC-VAL-005:** Cuenta inactiva → resultado=FALSE, motivo="cuenta_inactiva".<br>**TC-VAL-006:** Login durante bloqueo → resultado=FALSE, motivo="cuenta_bloqueada".                                                                                                                                                                                                                                                                                                                                                 |

<!-- 
Opción 2: Plantilla para Subcasos Simples

Para subcasos simples pero que aún merecen documentación separada:

| **Campo**           | **Descripción**                                                  |
| ------------------- | ---------------------------------------------------------------- |
| **ID**              | CU-XXX.Y                                                         |
| **Nombre**          | [Nombre del Subcaso]                                             |
| **Usado por**       | CU-AAA, CU-BBB                                                   |
| **Propósito**       | [Breve descripción: qué hace y por qué existe el subcaso]        |
| **Entradas**        | [Datos o parámetros que recibe del caso de uso padre]            |
| **Salidas**         | [Datos o resultados que retorna al caso de uso padre]            |
| **Flujo Principal** | 1. [Paso 1]<br>2. [Paso 2]<br>3. [Paso 3]                        |
| **Excepciones**     | [Descripción de las excepciones o errores manejados, si los hay] |


Opción 3: **Documentación Inline (No es Subcaso Separado)**

Cuando NO merece subcaso separado, documentar directamente en el flujo principal:

CU-001: Realizar Préstamo

Flujo Principal
1. El bibliotecario selecciona "Nuevo Préstamo"
2. El sistema solicita identificación del usuario
3. El bibliotecario ingresa carnet
4. **El sistema valida estado del usuario:**
   4.1. Verifica que usuario existe en BD
   4.2. Verifica que usuario.estado = "activo"
   4.3. Verifica que multas vencidas = 0
   4.4. Si alguna validación falla → Excepción 4a
5. El sistema muestra información del usuario
-->


<!--
## ERRORES COMUNES

### **Error 1: Documentar todo como subcaso**

**Incorrecto:**

CU-001: Login
  └─ CU-001.1: Mostrar Formulario de Login  ← NO merece subcaso
  └─ CU-001.2: Validar Formato de Email     ← Trivial
  └─ CU-001.3: Verificar Credenciales       ← SÍ es subcaso
  └─ CU-001.4: Crear Sesión                 ← Trivial
  └─ CU-001.5: Redirigir a Dashboard        ← Trivial


**Correcto:**

CU-001: Login
  Pasos inline: 1-10
  Paso 4: [Subcaso incluido: CU-VAL-001 Verificar Credenciales]
  Otros pasos: documentados inline


### **Error 2: Confundir subcaso con función técnica**

**Incorrecto subcaso:**

CU-LOG-001: Escribir en Log
  Propósito: Guardar mensaje en archivo de log

  Flujo:
  1. Abrir archivo log en modo append
  2. Escribir timestamp + nivel + mensaje
  3. Cerrar archivo


**Problema:** Esto es una **función técnica**, no un subcaso de uso. No tiene lógica de negocio, no le importa al usuario final.

**Correcto:** Documentar como función en documentación técnica, no como caso de uso.


### **Error 3: Subcasos demasiado granulares**

**Incorrecto:**

CU-001: Realizar Préstamo
  └─ CU-001.1: Validar Usuario
       └─ CU-001.1.1: Verificar Usuario Existe
       └─ CU-001.1.2: Verificar Usuario Activo
       └─ CU-001.1.3: Verificar Sin Multas


**Problema:** Demasiada granularidad. Los sub-subcasos rara vez son necesarios.

**Correcto:**

CU-001: Realizar Préstamo
  └─ CU-001.1: Validar Usuario
       Pasos dentro del subcaso:
       1. Verificar usuario existe
       2. Verificar usuario activo
       3. Verificar sin multas vencidas



### **Error 4: Mezclar subcasos con flujos alternativos**

**Incorrecto:**

CU-001: Login
  └─ CU-001.1: Login con Google      ← NO es subcaso, es alternativa
  └─ CU-001.2: Login con Facebook    ← NO es subcaso, es alternativa
  └─ CU-001.3: Login tradicional     ← NO es subcaso, es alternativa


**Problema:** Estos son **flujos alternativos** del mismo caso de uso, no subcasos.

**Correcto:**

CU-001: Login

Flujo Principal:
1. Usuario selecciona método de autenticación

Flujo Alternativo 1a: Login con Google
  1a1. Sistema redirige a OAuth de Google
  1a2. ...

Flujo Alternativo 1b: Login con Facebook
  1b1. Sistema redirige a OAuth de Facebook
  1b2. ...

-->


**Diagrama de Casos de Uso:**

[Incluya aquí un diagrama UML de casos de uso mostrando actores y casos de uso principales con sus relaciones (include, extend). Puede crearlo con herramientas como draw.io, Lucidchart, PlantUML, o incluso a mano]

[![](https://img.plantuml.biz/plantuml/svg/XLRDRXit4BxlKqpbGoNLSlNdfZ5i8vOi9G7iE92iNA8W62qfYGv5RhXSftLH8ASyG1-Xjvxx27cJF4c7vEvg_LC75cmjvnlEp3VVpFfPQj7OR2EZ7nXV2iNXxENp5vU3iza8TaQzSNTyMbh2ORVpz9TnBqe_29MWmGqa67_05P_QtoK7msEBQYLv1P2bFCQKmnyHm830AwCpnOPQQhEDvcpQC6x2UNvqOep-L3dvCuf-XB4sDsY02GeMYw__Ah0wQLdTMcXhjKl886pu5Jbfiq8bRZ30hhcn8aOP4Pvy8CVxYwpGAegii5J4SDPgjpi7CE4eXGlrsdpzXuZQQ60Spj5o8r3ELVqDDwc_-Tn5GuRGWejR8IyIApRqnB3XKZywEeAJs6h3KwXBP1h4pSTCSCDqmnaZT4Qe3SH22cs9DoDq3J250UoCnwFshzq2CaipPwICvceBzzYPmmw7Ws4HSYfIopVe8vGTWbfn7DmlURokaUU--_7Dea_m7sBgIy_eJsA4YaM24kenLzReLfebH8WseG8e-rrhDWEJpUPStUTohYfa-ho7CmB3pc1mEXeFgl6dsO9kr2beIdI5LB-WXpeb8ZF66yJwgKWJdOhRVRwRpnjAWL4A8uhFGloSnMtuzvs7FFprIYo4UsJ_a_dxRjLrmbT4hxbTSVtIe4enb-t9yELfe-BVg_e_vuexxw7U94OlK5dkuvQtLHpx3v05Eeb9qwvF_3VB5NCqJRaR3f8TWaJgA8bXZNTf6gbhGO5VQIkMHAFFTQuIxN8nXbS3xpkbZPyEomHkgv-dj1o88rYwaML8a9naQBrT2yQuUiVq9zMg49X_UnZGAm6zXm7zi28S3nCkqJ50enPh1PYFdIjs02qZLclREiurTm12aNWmci6Uj-oL1bowWI7AY807hZuyp5LuV0prhJmnzQhaANKiZ0ci7HM02xpIFeaGO6_lkEJae7hRFNltE_RUT-pzE_PRjRXk7Hu6eVXASl5igwYAfMX-URc_kl2UgxUn5mgLx2R6iVUk24Ug8lNeSYs6XYXQNk291xqCLrAdcysnpAveqb7Ih2cqubgd1yqccRvz_XlwU53CBoWDN56RhLVtjoz_-INUQUVGVOAUPv92_ppDqeIhiBOBNBV0FN6uVB3TdIoVUzgM1RRN3bgdtGzCnzc6kfiJoBX5APtEYGTmDKMXCicNsyByXddjrrc_jK_V9sEwjVkuJpVtWIU5G-TnXrxXqEaK7ctu2IQlw5kx_xXll_Jj5hwzYeVaA_VWs-MxD59B_J7ZeJEqN4ai0bVqwgVNSCRT4eJfnTa5hHook-SijXaT2kNRIhp9_9sx5xWz8sx2mizVEa9TwvWwwmv8Z0HPtbS6r4FFT_EUxlfbuGfl0Esribcqb-WZmP9WDM5S-7ZxXjiDOdA8eWoVbgivb1v5p-Yt-wVfFm00)](https://editor.plantuml.com/uml/XLRDRXit4BxlKqpbGoNLSlNdfZ5i8vOi9G7iE92iNA8W62qfYGv5RhXSftLH8ASyG1-Xjvxx27cJF4c7vEvg_LC75cmjvnlEp3VVpFfPQj7OR2EZ7nXV2iNXxENp5vU3iza8TaQzSNTyMbh2ORVpz9TnBqe_29MWmGqa67_05P_QtoK7msEBQYLv1P2bFCQKmnyHm830AwCpnOPQQhEDvcpQC6x2UNvqOep-L3dvCuf-XB4sDsY02GeMYw__Ah0wQLdTMcXhjKl886pu5Jbfiq8bRZ30hhcn8aOP4Pvy8CVxYwpGAegii5J4SDPgjpi7CE4eXGlrsdpzXuZQQ60Spj5o8r3ELVqDDwc_-Tn5GuRGWejR8IyIApRqnB3XKZywEeAJs6h3KwXBP1h4pSTCSCDqmnaZT4Qe3SH22cs9DoDq3J250UoCnwFshzq2CaipPwICvceBzzYPmmw7Ws4HSYfIopVe8vGTWbfn7DmlURokaUU--_7Dea_m7sBgIy_eJsA4YaM24kenLzReLfebH8WseG8e-rrhDWEJpUPStUTohYfa-ho7CmB3pc1mEXeFgl6dsO9kr2beIdI5LB-WXpeb8ZF66yJwgKWJdOhRVRwRpnjAWL4A8uhFGloSnMtuzvs7FFprIYo4UsJ_a_dxRjLrmbT4hxbTSVtIe4enb-t9yELfe-BVg_e_vuexxw7U94OlK5dkuvQtLHpx3v05Eeb9qwvF_3VB5NCqJRaR3f8TWaJgA8bXZNTf6gbhGO5VQIkMHAFFTQuIxN8nXbS3xpkbZPyEomHkgv-dj1o88rYwaML8a9naQBrT2yQuUiVq9zMg49X_UnZGAm6zXm7zi28S3nCkqJ50enPh1PYFdIjs02qZLclREiurTm12aNWmci6Uj-oL1bowWI7AY807hZuyp5LuV0prhJmnzQhaANKiZ0ci7HM02xpIFeaGO6_lkEJae7hRFNltE_RUT-pzE_PRjRXk7Hu6eVXASl5igwYAfMX-URc_kl2UgxUn5mgLx2R6iVUk24Ug8lNeSYs6XYXQNk291xqCLrAdcysnpAveqb7Ih2cqubgd1yqccRvz_XlwU53CBoWDN56RhLVtjoz_-INUQUVGVOAUPv92_ppDqeIhiBOBNBV0FN6uVB3TdIoVUzgM1RRN3bgdtGzCnzc6kfiJoBX5APtEYGTmDKMXCicNsyByXddjrrc_jK_V9sEwjVkuJpVtWIU5G-TnXrxXqEaK7ctu2IQlw5kx_xXll_Jj5hwzYeVaA_VWs-MxD59B_J7ZeJEqN4ai0bVqwgVNSCRT4eJfnTa5hHook-SijXaT2kNRIhp9_9sx5xWz8sx2mizVEa9TwvWwwmv8Z0HPtbS6r4FFT_EUxlfbuGfl0Esribcqb-WZmP9WDM5S-7ZxXjiDOdA8eWoVbgivb1v5p-Yt-wVfFm00)

[Complete con los casos de uso principales de su sistema. No necesita documentar TODOS los casos de uso con el mismo nivel de detalle. Enfóquese en los más críticos o complejos.]






### 4.2 Glosario

<!--
Glosario extendido complementando la Sección 1.4.
Incluye términos adicionales que surgieron durante la especificación detallada.
-->

[Si ya documentó un glosario completo en 1.4, puede referenciarlo:]

Ver Sección 1.4 para el glosario completo de términos, acrónimos y abreviaturas utilizados en este documento.

[O expandir con términos adicionales específicos del dominio:]

**Términos Adicionales del Dominio Bibliotecario:**

| Término | Definición |
|---------|------------|
| **Catálogo bibliográfico** | Registro organizado de todos los materiales disponibles en la biblioteca, con información descriptiva de cada uno. |
| **Clasificación Dewey** | Sistema Dewey de clasificación decimal utilizado para organizar libros por temas. Rango de 000 a 999. |
| **ISBN** | International Standard Book Number. Código único de 13 dígitos que identifica libros comerciales. |
| **MARC** | MAchine-Readable Cataloging. Formato estándar para representar y comunicar información bibliográfica en forma legible por computadora. |
| **Morosidad** | Estado de un usuario que no ha devuelto materiales en la fecha establecida. |
| **Obra** | Contenido intelectual (ej: "Don Quijote de la Mancha"). Una obra puede tener múltiples ediciones y ejemplares. |
| **Política de préstamo** | Reglas que definen cuántos materiales puede prestar cada tipo de usuario, por cuántos días, y si puede renovar. |
<br>

### 4.3 Diagramas del sistema

<!--
Incluya diagramas que ayuden a visualizar la arquitectura, estructura de datos,
flujos de información, etc.

TIPOS DE DIAGRAMAS ÚTILES:
- Diagrama de contexto (relación del sistema con su entorno)
- Diagrama de arquitectura de alto nivel
- Diagrama de componentes
- Diagrama de despliegue
- Modelo entidad-relación de la base de datos
- Diagramas de flujo de procesos críticos
- Wireframes/mockups de interfaces principales
-->

**4.3.1 Diagrama de Contexto del Sistema**

[Incluya diagrama mostrando el sistema y sus interacciones con actores externos y sistemas externos]

[![](https://img.plantuml.biz/plantuml/svg/VLRBRkCs5DthAswpwKm0mzEi2cCQZ2ofYG2_8Cf1fx4NZCGuH2JI9Qcaaw8VCyjPp6e-mJ_MIxqiMtQz2KBUnpdd7bxxapPKcIBF8972iB-D73pmXunBmv8dvwUKFNB180gys9tTJ098Cggru-XdBhPKqHmKImmLcup1FmxWPqoJvusIXKWzcKdryQFcsh2SNb_3X6-Up3WhsEb0cXYfch0RnPWu7OSWcHAoYVpCiao-Lg5IfKoLOJ3ECAyy_Hs94Vx6u9ShvzykTAgKVArXLqa-LSyjm7tU1vjdk46IFgSRpAMGCiof58C1a8eaZ4ljOgkTypFyPZ_WUl4y2WZSBgVkR4xWNVZsLy6PIkdxAi8fcSF5KXTKSJdqCiwmyagCcqdG2w0QYkeUMgcQn7qSNfUX3zsJVeARvbmWP4LJgLQYHbzcKdlLoMXfa934mTG5BvZ5aJkfeU_7Vt5vsLVXyd8btZN7ADaDquRlVWZeGgRloywrKQ1ZcLvt0i4VSH2LCleCcpzH8CMM8KlrlW-fwJmj14_ubcOhWI325ENbZpoXYSLY4Kx36aFEeUEmWrfClN2K2yWqNgo49vLY4e8C8nHMuOciAvZjsHAj42iHCOruKecL48sY6N_3OLJ3G-SMXqLQ7VoGBEOaZCExhWIXU3mdmOIL8_TsFrA-aIN_CHgVQgJz9tjG57noTVNXruf_LaMVmH_cMyMqL7GbujqtbVFQcBmvFurvudwUBsEeSCzduUocXjaOUd3_n5CSoZgLhs9mQ5xdqCf7eQLRyKtZs8vkx1oSSXZ7rKjrdLhaeykAlrFBS7JPqjnJYuA9wo6dW8nWIPPk5Cw7tYJ49n8SSrHsMGskMvkFxFxGHMOe9DJilcRIZYTYec0l5BPgzmrNSovnJhSqORXdDHgGQgV97sJiqTPh6enW9XjNIy4qO117mwCtfCehgqDESJgSPaoVvZ0EnvDm7WUUPL8pE1f0dqV4DkKkEG1TldGfQ8CFZnPA9anR-x_8hAXGzkWSTXl10Nmcm72MRoNAOH-pcp5bq81VG1nmFqtEzQVX3FT8vFhpg5czvRexFPn7lYcGLNrcAGc6_oksbSgmBaTLF-O-dQg-rQXA0aoXwUux9YPMaudSQBiOQP5ojDpk-nbpDTjtkfo5NhXezs_RhsM0Js44TxXFKWgyt7GfJLSYuGN-fS8slR-DumKPufTI3EuYN5VlfqQyby2dHcgGA6lfc6wDCo23w2wqsjeLUHuWliaH1E85oHxD3Q7Pr64y8UlwyVPGbOFfE0BBoF_Np0_mcA1c_lmSg7eRs3dLayI969dlljPpkbVwYqY6XDokszNHWqOCDONkkE4ah8CLNk5fzasVRBMshKCUwgrzloHZk0tzTP_5VWzRcN8gB8_giFgYkm-8DyJcQmS_dvX8yOVVVm00)](https://editor.plantuml.com/uml/VLRBRkCs5DthAswpwKm0mzEi2cCQZ2ofYG2_8Cf1fx4NZCGuH2JI9Qcaaw8VCyjPp6e-mJ_MIxqiMtQz2KBUnpdd7bxxapPKcIBF8972iB-D73pmXunBmv8dvwUKFNB180gys9tTJ098Cggru-XdBhPKqHmKImmLcup1FmxWPqoJvusIXKWzcKdryQFcsh2SNb_3X6-Up3WhsEb0cXYfch0RnPWu7OSWcHAoYVpCiao-Lg5IfKoLOJ3ECAyy_Hs94Vx6u9ShvzykTAgKVArXLqa-LSyjm7tU1vjdk46IFgSRpAMGCiof58C1a8eaZ4ljOgkTypFyPZ_WUl4y2WZSBgVkR4xWNVZsLy6PIkdxAi8fcSF5KXTKSJdqCiwmyagCcqdG2w0QYkeUMgcQn7qSNfUX3zsJVeARvbmWP4LJgLQYHbzcKdlLoMXfa934mTG5BvZ5aJkfeU_7Vt5vsLVXyd8btZN7ADaDquRlVWZeGgRloywrKQ1ZcLvt0i4VSH2LCleCcpzH8CMM8KlrlW-fwJmj14_ubcOhWI325ENbZpoXYSLY4Kx36aFEeUEmWrfClN2K2yWqNgo49vLY4e8C8nHMuOciAvZjsHAj42iHCOruKecL48sY6N_3OLJ3G-SMXqLQ7VoGBEOaZCExhWIXU3mdmOIL8_TsFrA-aIN_CHgVQgJz9tjG57noTVNXruf_LaMVmH_cMyMqL7GbujqtbVFQcBmvFurvudwUBsEeSCzduUocXjaOUd3_n5CSoZgLhs9mQ5xdqCf7eQLRyKtZs8vkx1oSSXZ7rKjrdLhaeykAlrFBS7JPqjnJYuA9wo6dW8nWIPPk5Cw7tYJ49n8SSrHsMGskMvkFxFxGHMOe9DJilcRIZYTYec0l5BPgzmrNSovnJhSqORXdDHgGQgV97sJiqTPh6enW9XjNIy4qO117mwCtfCehgqDESJgSPaoVvZ0EnvDm7WUUPL8pE1f0dqV4DkKkEG1TldGfQ8CFZnPA9anR-x_8hAXGzkWSTXl10Nmcm72MRoNAOH-pcp5bq81VG1nmFqtEzQVX3FT8vFhpg5czvRexFPn7lYcGLNrcAGc6_oksbSgmBaTLF-O-dQg-rQXA0aoXwUux9YPMaudSQBiOQP5ojDpk-nbpDTjtkfo5NhXezs_RhsM0Js44TxXFKWgyt7GfJLSYuGN-fS8slR-DumKPufTI3EuYN5VlfqQyby2dHcgGA6lfc6wDCo23w2wqsjeLUHuWliaH1E85oHxD3Q7Pr64y8UlwyVPGbOFfE0BBoF_Np0_mcA1c_lmSg7eRs3dLayI969dlljPpkbVwYqY6XDokszNHWqOCDONkkE4ah8CLNk5fzasVRBMshKCUwgrzloHZk0tzTP_5VWzRcN8gB8_giFgYkm-8DyJcQmS_dvX8yOVVVm00)

**4.3.2 Diagrama de Arquitectura de Alto Nivel**

[Incluya diagrama mostrando capas principales: Presentación, Lógica de Negocio, Acceso a Datos, Integraciones]
[![](https://img.plantuml.biz/plantuml/svg/XLVDSjis4BxpARQ-r7RYPZAPNZoTJ6LQSTMnVYegwNJg7Y0Iek6000k0IfnEhts0vWbop26dt7hLc_H9kWl-YtBZWqVS_G0illsm2tnl7JEko2GmytiX78zTOTXPp79cWwyIlX6AGpYVBkQpyMm51lrCfP87WNqjLCuCoo3MMQuLLmx-203_BbZyEZMwK4cefJRVVPSRRj7DOg7Ly-TmBT9RTo4BVXYjUAeHMGEl3EVgC39XJjiQzmkNKhyv31JAyTJqrby8zVems1ccx9ORosGR0xilmTeat7WWN4WSwQqlj7AHUCVXwTFWpoup621RCyiF4mC_ttBc7fWNvt72IGwNWc7e6OE4mwYJ8_yjdOQPs789Pn09wpZYBiHQ2htYyUsDEjuVyGn2IYqyWeYRhK16x4aGvBWYIpaSXQF522x7i5YE8yptA9piti-EO932SZ-_Jf1Nis7lu6U-lb5BRb47LcpPRu1BlE7h4ZLQJ03dMs4uBmeAvCJxMIwyt_zJsd4mn3NeJJCKuFGKDwAGbtJtYPsVdbRcC_XXDRt-zZ64KVJiCVp8jYoAZSXTux_GsbbCPVvaoZ18mIHSSYjIrI12b2rpI1O_X_3Mw8m_XXV2y8r--xW20OoJ5CqHsp1JHijLueEb10rekzwzlvg4_kTiV3KF9tFYhXLqHTjqzpaffCPytAXHuP1N4IEpky_gHjrZOjB2Y8Gb9Kk5knsEkkBM4Tv_lBG5HgUjnnVLnnV6XCpjFY2hsW-AKQVqCHoqCBkFM28oRU7-HbtohPO5QO2Ngv4il7Su4jM02cCbpbGVGzYqa0u1zx1WQRM5p9k6q9bsOkEPQjPNP3gqTgwDu_NQvST3OciO9hLL6cPh8Ia5t7OrzugHqISAOiCJhcBKLJLpAIdbZ9Pqq5WSSwlXU7an2ayQG2S7O56Ej95MibB_Nd0D62vGnL9OtM3392vQ4Vo_uXk5uJYQ0_uUhUOH2Q-kZvNiY1Khd4Pvx8c6AEeBfuUjJr27qAmn7S2tecdmUqBfmVUKWjllgQKVYjT66qP7AZtSg4Ze9nQD1il8z9081WoG61RC6KfMC_DzLmsZDTMN9jDOU2yRtoJB9S-eO4AuVDdQfqpnEmQ-nU2uVlvVMWRpvHIETKuU9ay6IMyQoj45_KSLNLAEaN9jNMfuzDCrLjdjqsUFJevet-i4atz8BD5u-Mg2zIcYZybiDRvQjiM-touhzOHIu7wmvomcDwhkDTD2OG_9cVGisqp49Qe_99gk5ZTgd35HurpU0zQzg2uSE65ILgOr1bxajl8_bBszXIbt8JRW63Mw-sIfklREiSy2BGPEP5mNhit1aZSd3-k2pdOVSBHk_I_mE59CcEvC9neofWecsm8WJ8pz5jQ6izVS03OOZ44DyXXBNIHmLD5eOVoMODeUrMmF2BvH6EuaeLwngRj5JNg7n0HhHqdtHE76NL4ggQ5z3_eGtsRRKqshbjLoD8jUZPVHw7hiQqp_jbH5VwtJLAYKMiRUGPIbfuJrEv9M6u6ThrlUOs-hnCJYszt7gbt5jvLowfBS3Dbs30_9fHi4QMMKIwGKK-fqGZ7w9VA-PfOynPGOhngTSyFs3c-bgHWJP324TopnK6uCbRCMjlle3EcHd0Ob8JBIhHuev6jSKLQB04tAovZWU2CBBrwBQv4U-4c0zoKuEtlkMncSGwHnFvXxnE0zQRLe_4s5gmrDuwyDRPskBKqnhWrLpMtzLNiD_EgrgLcg_l45J-S8rq4r8phDfeclSROH3tt_Ex29e-yghnJrhjijrZGCF9r5IcfQJydKdhKDkAPk6DB0qrbau6id3BgJUFyw2Vh3kzR-nYjZRt_ry7O7bSKtqzeGjCchSuag9EL5J-ZY7tGAVWLmEUaK2zMJrNKKzAjyEMrTY11dxBsAdqJH3q7WizFCKIkcVrhgUInqYXCILnrx-2RHRzGtpMb1yz3NaFY0lwNk0K27aWeHbDNiC29kgnyMn26qvUzBM6pvvzXtpEv3nh5U-IBAttfau0jdWspEsRclgBkF1BMbPll83XiLqbyjWw1RRG-XUzNu8BWJn9V1NTPxw43obAgdB_61lxij9xDmig2UDLh-z7Ao6eShlDvCmddagxe7HPpUwUM5dgloQLmMVMpbB66-vE8bWIigrhsN0Up-mSxCFFIIvxuKusi07s1A9FYAZCl6Yy4VCsF4ci6_V_qDU7cxqoVL_3YrBR2L26p4ipcHhsCEehawnlLBmKSXrCP3wzXV4UIkZVVq55iGNbr45I3QSOriJOcGEgvwalMl2vgm6hGYHZj35gRWwt8R3hF81WF65kTYlKMeBUK5lOU0Uo-zNn9FYjTiLjtCplm3gx3TqTMpZQxeXHCKvBfyLFXDufDzkxTFlEdIcnqqdkjRZedeDr8upeGJARLV9BIIQydubDtJLZGHVETpAEXonIGStnMsl5TXpcc_MO_Aam3dBnKM1D_Z_oAJ_m40)](https://editor.plantuml.com/uml/XLVDSjis4BxpARQ-r7RYPZAPNZoTJ6LQSTMnVYegwNJg7Y0Iek6000k0IfnEhts0vWbop26dt7hLc_H9kWl-YtBZWqVS_G0illsm2tnl7JEko2GmytiX78zTOTXPp79cWwyIlX6AGpYVBkQpyMm51lrCfP87WNqjLCuCoo3MMQuLLmx-203_BbZyEZMwK4cefJRVVPSRRj7DOg7Ly-TmBT9RTo4BVXYjUAeHMGEl3EVgC39XJjiQzmkNKhyv31JAyTJqrby8zVems1ccx9ORosGR0xilmTeat7WWN4WSwQqlj7AHUCVXwTFWpoup621RCyiF4mC_ttBc7fWNvt72IGwNWc7e6OE4mwYJ8_yjdOQPs789Pn09wpZYBiHQ2htYyUsDEjuVyGn2IYqyWeYRhK16x4aGvBWYIpaSXQF522x7i5YE8yptA9piti-EO932SZ-_Jf1Nis7lu6U-lb5BRb47LcpPRu1BlE7h4ZLQJ03dMs4uBmeAvCJxMIwyt_zJsd4mn3NeJJCKuFGKDwAGbtJtYPsVdbRcC_XXDRt-zZ64KVJiCVp8jYoAZSXTux_GsbbCPVvaoZ18mIHSSYjIrI12b2rpI1O_X_3Mw8m_XXV2y8r--xW20OoJ5CqHsp1JHijLueEb10rekzwzlvg4_kTiV3KF9tFYhXLqHTjqzpaffCPytAXHuP1N4IEpky_gHjrZOjB2Y8Gb9Kk5knsEkkBM4Tv_lBG5HgUjnnVLnnV6XCpjFY2hsW-AKQVqCHoqCBkFM28oRU7-HbtohPO5QO2Ngv4il7Su4jM02cCbpbGVGzYqa0u1zx1WQRM5p9k6q9bsOkEPQjPNP3gqTgwDu_NQvST3OciO9hLL6cPh8Ia5t7OrzugHqISAOiCJhcBKLJLpAIdbZ9Pqq5WSSwlXU7an2ayQG2S7O56Ej95MibB_Nd0D62vGnL9OtM3392vQ4Vo_uXk5uJYQ0_uUhUOH2Q-kZvNiY1Khd4Pvx8c6AEeBfuUjJr27qAmn7S2tecdmUqBfmVUKWjllgQKVYjT66qP7AZtSg4Ze9nQD1il8z9081WoG61RC6KfMC_DzLmsZDTMN9jDOU2yRtoJB9S-eO4AuVDdQfqpnEmQ-nU2uVlvVMWRpvHIETKuU9ay6IMyQoj45_KSLNLAEaN9jNMfuzDCrLjdjqsUFJevet-i4atz8BD5u-Mg2zIcYZybiDRvQjiM-touhzOHIu7wmvomcDwhkDTD2OG_9cVGisqp49Qe_99gk5ZTgd35HurpU0zQzg2uSE65ILgOr1bxajl8_bBszXIbt8JRW63Mw-sIfklREiSy2BGPEP5mNhit1aZSd3-k2pdOVSBHk_I_mE59CcEvC9neofWecsm8WJ8pz5jQ6izVS03OOZ44DyXXBNIHmLD5eOVoMODeUrMmF2BvH6EuaeLwngRj5JNg7n0HhHqdtHE76NL4ggQ5z3_eGtsRRKqshbjLoD8jUZPVHw7hiQqp_jbH5VwtJLAYKMiRUGPIbfuJrEv9M6u6ThrlUOs-hnCJYszt7gbt5jvLowfBS3Dbs30_9fHi4QMMKIwGKK-fqGZ7w9VA-PfOynPGOhngTSyFs3c-bgHWJP324TopnK6uCbRCMjlle3EcHd0Ob8JBIhHuev6jSKLQB04tAovZWU2CBBrwBQv4U-4c0zoKuEtlkMncSGwHnFvXxnE0zQRLe_4s5gmrDuwyDRPskBKqnhWrLpMtzLNiD_EgrgLcg_l45J-S8rq4r8phDfeclSROH3tt_Ex29e-yghnJrhjijrZGCF9r5IcfQJydKdhKDkAPk6DB0qrbau6id3BgJUFyw2Vh3kzR-nYjZRt_ry7O7bSKtqzeGjCchSuag9EL5J-ZY7tGAVWLmEUaK2zMJrNKKzAjyEMrTY11dxBsAdqJH3q7WizFCKIkcVrhgUInqYXCILnrx-2RHRzGtpMb1yz3NaFY0lwNk0K27aWeHbDNiC29kgnyMn26qvUzBM6pvvzXtpEv3nh5U-IBAttfau0jdWspEsRclgBkF1BMbPll83XiLqbyjWw1RRG-XUzNu8BWJn9V1NTPxw43obAgdB_61lxij9xDmig2UDLh-z7Ao6eShlDvCmddagxe7HPpUwUM5dgloQLmMVMpbB66-vE8bWIigrhsN0Up-mSxCFFIIvxuKusi07s1A9FYAZCl6Yy4VCsF4ci6_V_qDU7cxqoVL_3YrBR2L26p4ipcHhsCEehawnlLBmKSXrCP3wzXV4UIkZVVq55iGNbr45I3QSOriJOcGEgvwalMl2vgm6hGYHZj35gRWwt8R3hF81WF65kTYlKMeBUK5lOU0Uo-zNn9FYjTiLjtCplm3gx3TqTMpZQxeXHCKvBfyLFXDufDzkxTFlEdIcnqqdkjRZedeDr8upeGJARLV9BIIQydubDtJLZGHVETpAEXonIGStnMsl5TXpcc_MO_Aam3dBnKM1D_Z_oAJ_m40)

**4.3.3 Diagrama de Componentes del Sistema**

**[Incluya diagrama mostrando los principales componentes/módulos del sistema y sus interacciones]

**Módulo de prestamos**

[![](https://img.plantuml.biz/plantuml/svg/ZLMxRjim5Dtr5RUURC11ban5KIIMtGQ5dRgnaux1DNNZig18bQGC64K_fcE6JDcwwiTAwcN9bjfuiKoUS-xHVVdIMDGsZGKm5ITAahHapZPy8xYonBu5RxXa8eq8teKNv-75GrZ1tWU1vLOGJ3bkDSO83XGUHE0C5jbBb0hbBvOwUtAXOcM285JI8fUa7oOgbH7g_H2JP0o3gqHmXendBn8ckOMrip0OmSy0tASM7oQQSZ6lf9KGf1sx_86Hqks80tUvIZINMrZSXt0W-Oi5IlgEeEb7wZGDNA_NIqXG8oIr0EoTu4w9b74Ntmn6FNPMf7USaG-NFt7LOQJ0m1ptXO5vzh9rR-sHahRAaTx23WMFi8Ws1fRz5ipbqJrgsWeq7bkxEt5Ja5qM3dRkgwD-FpL_KEF1lrMa83KfQgx6477ZC7p3SpM8qPBcACOWikUOsuxCCFJEVMGyk0aFXzxF1rTZxFTIek4nXtb2LGlV9eQssHy9YN8Mh4lZgGMfB7zqDws4DEjpKmBAulRvcCbTzemWM-X_LwBgYrjANFO6_ijmgtHNNtnQNa4DsFkJAyR8A70vGglQaKxVignHTwIxulBLST8AVnobgdXtc4LvIwyE51yOe-1NOpDCDyDeuoWJDBxUCFKChx5KncurhRxCSqKH8oFPdDLnxNxSbg-rXoQsILLbFnEhnNgPLpX6Bi0V5vFPNV74CPZIcdozWriIdTleT2NCXT-Hw8NZxCcgg4X1EVDEgobLqpg6-Sxa8lcEAgvr7xjp_9hy4g3BwUhJwPoXfau5w7LoD0fBqeORIowJicoMaddwmktMTaasgR1vwFP-wXKuwjgcGdkZ7Paly7aVpedEPuPflg7SxdGIbk2MkmfxX6aR-8zWLwxBZYqRadoV5elATUxvUhxodRYw_lprOJxxEBkP3aV19Sd8_Ql_1G00)](https://editor.plantuml.com/uml/ZLMxRjim5Dtr5RUURC11ban5KIIMtGQ5dRgnaux1DNNZig18bQGC64K_fcE6JDcwwiTAwcN9bjfuiKoUS-xHVVdIMDGsZGKm5ITAahHapZPy8xYonBu5RxXa8eq8teKNv-75GrZ1tWU1vLOGJ3bkDSO83XGUHE0C5jbBb0hbBvOwUtAXOcM285JI8fUa7oOgbH7g_H2JP0o3gqHmXendBn8ckOMrip0OmSy0tASM7oQQSZ6lf9KGf1sx_86Hqks80tUvIZINMrZSXt0W-Oi5IlgEeEb7wZGDNA_NIqXG8oIr0EoTu4w9b74Ntmn6FNPMf7USaG-NFt7LOQJ0m1ptXO5vzh9rR-sHahRAaTx23WMFi8Ws1fRz5ipbqJrgsWeq7bkxEt5Ja5qM3dRkgwD-FpL_KEF1lrMa83KfQgx6477ZC7p3SpM8qPBcACOWikUOsuxCCFJEVMGyk0aFXzxF1rTZxFTIek4nXtb2LGlV9eQssHy9YN8Mh4lZgGMfB7zqDws4DEjpKmBAulRvcCbTzemWM-X_LwBgYrjANFO6_ijmgtHNNtnQNa4DsFkJAyR8A70vGglQaKxVignHTwIxulBLST8AVnobgdXtc4LvIwyE51yOe-1NOpDCDyDeuoWJDBxUCFKChx5KncurhRxCSqKH8oFPdDLnxNxSbg-rXoQsILLbFnEhnNgPLpX6Bi0V5vFPNV74CPZIcdozWriIdTleT2NCXT-Hw8NZxCcgg4X1EVDEgobLqpg6-Sxa8lcEAgvr7xjp_9hy4g3BwUhJwPoXfau5w7LoD0fBqeORIowJicoMaddwmktMTaasgR1vwFP-wXKuwjgcGdkZ7Paly7aVpedEPuPflg7SxdGIbk2MkmfxX6aR-8zWLwxBZYqRadoV5elATUxvUhxodRYw_lprOJxxEBkP3aV19Sd8_Ql_1G00)

**4.3.4 Modelo Entidad-Relación de la Base de Datos**

[Incluya diagrama ER mostrando entidades principales y sus relaciones]

Ejemplo de entidades principales:
- Usuario (id, carnet, nombres, apellidos, email, tipo_usuario, fecha_registro, estado)
- Material (id, isbn, titulo, autor, editorial, año, categoria, ubicacion)
- Ejemplar (id, material_id, codigo_barras, estado, fecha_adquisicion)
- Prestamo (id, usuario_id, ejemplar_id, fecha_prestamo, fecha_devolucion_esperada, fecha_devolucion_real, estado)
- Multa (id, prestamo_id, monto, fecha_generacion, fecha_pago, estado)
- Reserva (id, usuario_id, material_id, fecha_reserva, estado)

[![](https://img.plantuml.biz/plantuml/svg/jLbDRzl86RxhLmoCNTWMRCDEugOGDa5eYKgOIAIMaepTee0m8iVA92I76PBEUZUzzjP3sr-mnnvoAFQsL_sJ_fA-yyKlKNRQRGF446VUuRmVp_l95rcEULx44OfPI29sIlZfcguZod8IlEtr3j6G9JTqKt0SqEql2Ge98bbE8vRrilSqIJ77CGeYd6Nefnw2VrSuUB_Xh4Z28OiOHnEwUPj_JwA8VLJxZ8U4gxsh28ZbgiKv-wWMHvY_lueAqljJhvVJF29eAbb3TfBJ48UdFeaqCwTeJhESn1XTIPuNmFCVawCHnHjW2mlU0vBc1OwEXIYskt16rcY0blEbvJlUwigvcZZUmXvQw2Y8A4boaWa98unA9U3Z7gpJ_0uTzFkx1_lz0uGpL6G5vfHf7VHHlq_3bLxizz40EUx2Vcdxw9jlPc-UFvTKfwUQEC0y8JaGNLl-y9Nb7pqwFmR2fUjykxGrSH_bD6Mha0L53FmmeBRTvVJeS6YFbXFhyEHmPisjcUSlxCDZVI81KjuyS-yD2OlN73HGaLsSdvkNuHHiI4EsP_i6L8zN2HWcflgkaRMmzMv8EGa2of862-NXd4JaXYNieicXt3LxZphs-WXiJwCMHtjKPqna56U1tXOUACwUBvOZnm83mOFZZk6NCpbi2iR91f36MsAfFV93IeLxi6GL4wb1Yfjqu34uhDqyN3ZNukRvSZwptP4pykJDUbtT71THZhDLIf9G0nDUQG-TgJK1AKyUAIgspWY_bPTBYeNztQB170u4_EcFM6j_uKn1Nciw4-xLuH9pPxwmf-0FAU4PIt24FXG4u8qHYL2clAtB8_IvfZje-awlMEdD1xsZ00aJ79EQbI-xZ9n23Fe8mMNr5cTlws2vl3Isv2ogcN_gkC2qRuqy7zHVkJI80y-MbCYjkzDlS8ylm-a-dBIWGG4Eu6BPwWQNTneDZkon1RX6vv9o7J4m7xnJA2N73VlNKH9miWiGGQ2s0OeqPe2bW6HiXuQcEmH6p2UW-YREfk0LlcDDQX0oInexCSu9fm2y1chCwWDmeTcw7cCkddP6Wxo8wbm-hfcno1bVfPmc0Krnr1Mk90d9LXa98Cb9c3UWMKKr4NLAQOnH9ywLBspgszS0C16uHzSZ-3iKVxo5RunCGWhtKDn6ZU9X-q-sIWj8KO6nczQ9ETiAjfVw80qfYt77HW1yRiHzgv1y97UTmRQawM8f95d0QMfGPE9GiTOihcve1Z_tk8S4_cf34i9hkXevyvddWcEAoEnwgzgp5YV6S6QLCWxd0QSywZQ5WZ5DDc2uClAO6Dq4gFtQdiucbWyL0KifuF5c-ramBWk38YdXMG-2ven6C7b7uZJ2l8bWixeFmVS3VRnRDR2GRjXgZJd7sVt1KHS29LzDjEp4dORQPxvmTPcXR7VbspFBjuQEvuejszUvwyfwRRKo9Wu_5CBY2WzbCaoX483Wtzhz_-KrnVxKgrdBB6bh0KSWVjogtSpg0zRgBl76BQezfc-JjJ9ZMNJiEzPn92ItB2gQ8U4-z9J2rwDXHynKIgzHT-UHwleLoQ220AUi6t-72D9ErF6oVNbmP5ylRLMqNTlkK67Fe5278IgAfehFEj0Re6e8Oz3Lf6Weyxz68A3Dzg-j6W3rYiOVi27kRC9FB_vFqFV54SMKkegV1yqYIrTRbSskjt36pb35YQ47qT3MGMDekKDxeWF8TpD7r5lQLhfdO3czgV9OL_rHLTYxQ0eOk1RHZ3KFTmQHLZa2jLBTDFBP52AY0czL8MBf0QFiYHnxdFr1ewWgGh9Y5E_RKBNEA-pB8iBQ_jKhGt3CT0ks4rYDbLMgRQlqNXlFh9UMl6lekIFF5R_hTapnfj4UnIHdaDFridgTFRQDBoyi_xKjwnyGnfsFRLzuT9L5xec7NnmDzTqTn5y03GDfaUng2AalQw0q4Dp0Ittdj_bo0m-bFcKKd0e3oV2eyxOp4HB0WaIpx6ri5qWLKguc7aJs2YiuAzgpWR9kYacIuNUaA_obdCaXIxWRARJJ9hUqQ_TUZ06VZWBPs9e8CKmrBFed2CXPJfCwhsKDMVP4ujgwqPiD4U4Swdj3qs7rYVToPIr7piA3bgHcziQwjZike4Pl6ZnYcmSRMcYLP8H8ErGZlPtSjgOrjKfv5-KFUWC6UsY5Dyi-l7Saa-DrXCt1hdP1fYZbZVlU7s9X3fo8vCDKt_nw3gvKxIK59DZ6Ubyqaz1XG7HgTP7o58JvA6hvgm_9HVYYFU-P2S-dJwUdx2TKI_07EOLuTz2cg5BTWQX489Vla9Z8k-SDhUHr8AhRDP3rohvF4zPgR_KgfDgBWntA6bEah0v21kyitz4X8365hAGiToJbfqeA5VQ1eZMXwNYZjYz6HodV_aCk7n_yH-TC_RJz9TbxikJC77kG409FG3ACH73VHwmyioul68eWBcRHYDsO-HIWIbHZBoVM7E84SksN7a1fqE_3nYaQgh7izjU41WofDm7AHVyVRt_EmUfYgaeahItdEvhq3j9BH3TOzEzCRY_g0qY0CU4nJK045cq_vwQvBDKyqBwW9fG3f6OtbsNhIR8JT769mkrdd6dIQePfo1ytoSyRv6RAQOWVDOYVbhGWc8hLrQGIPLJF9j5pzDMZSqarLNDFE8LKhOOkv8n2J0NI0iI27n4o4GF2QYWyXxJDOc1qlrtsjne1Ze8Y4hyoiW5Zg5XMr_rTSofJ5n7CkQOOOQHRYov38o6zl1-fyXzqi9STINzdijqpfDeOUQLLAWEykUOcnlBTZHAyufNdMqVDgGaicxx8hEiuSLOHb1szl7vEuNguEsF0lqO6-jUV_wP1pikokDjCvltIJ6ewC3V6gMuQeBGW4jQ23PufHp7ZX06245yYNcYJtYfVQKmP1i00z7HPoXAwZWW29qyPnr7bURhzW_Vz01A9aeETQ3aKJYML650C8Es40f9eZT_X4_7cW781622HiYohyOvcFXSlGl7srmXm8rAFaPraKc1RFZA8D2D80DyMz1rewW0TNLHp8gbO8BsidGMHRWYNO_szMZRCz_iBP-RDqVTewa6TLsfQTm43zDNvsUKvn18k3IdaqyQjwGU47x8iPsetPMBqeZxdHQZX3BAFWChi5aU5q9PuRVKjJCKpfIljKG78hUD1MSZDLMWmdBgUrgPEiXpfp5_QF-jqn2hej9MqPZdufj2Ipe-IfV5a-TeJ0KCtsEh-YpDaU3MfjJGoS5Q12sWVdHacdbNImFhZC-6oqXzl2K0PrTHsOZwB8Eb-Chn3FLHUTbS9L7N9GFha3CtXHScjZ9eoVm17LMQwhFXM1SEJtxz5udkhC2-4ME5-lplJlWpFWoeUL0quq3oLD0dR9JFjkEBxgDJA1p0MhdkTl9L1vCwEQvQ8o4OyIC1A_KDVA6EdACQKxlk26QXqMJqZeYFG0tANaua8PAf25dGHlYLencaCCcEvCwxlZ1dV_fmGjMF6Kx1xZSLNOvrw8QX4M9Ml1gYkvqCBxFm1uidsxwx1v8A5WDW8_alYJ9nyF7RHqOBmGCGEk0vCweg_qR6Eci9Vn0SvaWHYCWnEbcGK0fVEbOA0ar1y5H04mjTaeMiusVu543K4x_1ji130gnuufP329PJy6JggyWyxhfFSQ4K02HTV1_K7rtUC9faYr20wKn-MJyhdzWTXIMpCVYQ-dSYLCdyqHinoosJeizRyiBbvNqeyLT52voQvK2-YzVh9JfTfb0WW4n_jeDEeLFVA7huPx4cQpv-rXfVt7YbBYNkFgV4Aa9pNLvKFJvmtDZhy-iNNXy9Lb8_qUY_WRn57_mO0)](https://editor.plantuml.com/uml/jLbDRzl86RxhLmoCNTWMRCDEugOGDa5eYKgOIAIMaepTee0m8iVA92I76PBEUZUzzjP3sr-mnnvoAFQsL_sJ_fA-yyKlKNRQRGF446VUuRmVp_l95rcEULx44OfPI29sIlZfcguZod8IlEtr3j6G9JTqKt0SqEql2Ge98bbE8vRrilSqIJ77CGeYd6Nefnw2VrSuUB_Xh4Z28OiOHnEwUPj_JwA8VLJxZ8U4gxsh28ZbgiKv-wWMHvY_lueAqljJhvVJF29eAbb3TfBJ48UdFeaqCwTeJhESn1XTIPuNmFCVawCHnHjW2mlU0vBc1OwEXIYskt16rcY0blEbvJlUwigvcZZUmXvQw2Y8A4boaWa98unA9U3Z7gpJ_0uTzFkx1_lz0uGpL6G5vfHf7VHHlq_3bLxizz40EUx2Vcdxw9jlPc-UFvTKfwUQEC0y8JaGNLl-y9Nb7pqwFmR2fUjykxGrSH_bD6Mha0L53FmmeBRTvVJeS6YFbXFhyEHmPisjcUSlxCDZVI81KjuyS-yD2OlN73HGaLsSdvkNuHHiI4EsP_i6L8zN2HWcflgkaRMmzMv8EGa2of862-NXd4JaXYNieicXt3LxZphs-WXiJwCMHtjKPqna56U1tXOUACwUBvOZnm83mOFZZk6NCpbi2iR91f36MsAfFV93IeLxi6GL4wb1Yfjqu34uhDqyN3ZNukRvSZwptP4pykJDUbtT71THZhDLIf9G0nDUQG-TgJK1AKyUAIgspWY_bPTBYeNztQB170u4_EcFM6j_uKn1Nciw4-xLuH9pPxwmf-0FAU4PIt24FXG4u8qHYL2clAtB8_IvfZje-awlMEdD1xsZ00aJ79EQbI-xZ9n23Fe8mMNr5cTlws2vl3Isv2ogcN_gkC2qRuqy7zHVkJI80y-MbCYjkzDlS8ylm-a-dBIWGG4Eu6BPwWQNTneDZkon1RX6vv9o7J4m7xnJA2N73VlNKH9miWiGGQ2s0OeqPe2bW6HiXuQcEmH6p2UW-YREfk0LlcDDQX0oInexCSu9fm2y1chCwWDmeTcw7cCkddP6Wxo8wbm-hfcno1bVfPmc0Krnr1Mk90d9LXa98Cb9c3UWMKKr4NLAQOnH9ywLBspgszS0C16uHzSZ-3iKVxo5RunCGWhtKDn6ZU9X-q-sIWj8KO6nczQ9ETiAjfVw80qfYt77HW1yRiHzgv1y97UTmRQawM8f95d0QMfGPE9GiTOihcve1Z_tk8S4_cf34i9hkXevyvddWcEAoEnwgzgp5YV6S6QLCWxd0QSywZQ5WZ5DDc2uClAO6Dq4gFtQdiucbWyL0KifuF5c-ramBWk38YdXMG-2ven6C7b7uZJ2l8bWixeFmVS3VRnRDR2GRjXgZJd7sVt1KHS29LzDjEp4dORQPxvmTPcXR7VbspFBjuQEvuejszUvwyfwRRKo9Wu_5CBY2WzbCaoX483Wtzhz_-KrnVxKgrdBB6bh0KSWVjogtSpg0zRgBl76BQezfc-JjJ9ZMNJiEzPn92ItB2gQ8U4-z9J2rwDXHynKIgzHT-UHwleLoQ220AUi6t-72D9ErF6oVNbmP5ylRLMqNTlkK67Fe5278IgAfehFEj0Re6e8Oz3Lf6Weyxz68A3Dzg-j6W3rYiOVi27kRC9FB_vFqFV54SMKkegV1yqYIrTRbSskjt36pb35YQ47qT3MGMDekKDxeWF8TpD7r5lQLhfdO3czgV9OL_rHLTYxQ0eOk1RHZ3KFTmQHLZa2jLBTDFBP52AY0czL8MBf0QFiYHnxdFr1ewWgGh9Y5E_RKBNEA-pB8iBQ_jKhGt3CT0ks4rYDbLMgRQlqNXlFh9UMl6lekIFF5R_hTapnfj4UnIHdaDFridgTFRQDBoyi_xKjwnyGnfsFRLzuT9L5xec7NnmDzTqTn5y03GDfaUng2AalQw0q4Dp0Ittdj_bo0m-bFcKKd0e3oV2eyxOp4HB0WaIpx6ri5qWLKguc7aJs2YiuAzgpWR9kYacIuNUaA_obdCaXIxWRARJJ9hUqQ_TUZ06VZWBPs9e8CKmrBFed2CXPJfCwhsKDMVP4ujgwqPiD4U4Swdj3qs7rYVToPIr7piA3bgHcziQwjZike4Pl6ZnYcmSRMcYLP8H8ErGZlPtSjgOrjKfv5-KFUWC6UsY5Dyi-l7Saa-DrXCt1hdP1fYZbZVlU7s9X3fo8vCDKt_nw3gvKxIK59DZ6Ubyqaz1XG7HgTP7o58JvA6hvgm_9HVYYFU-P2S-dJwUdx2TKI_07EOLuTz2cg5BTWQX489Vla9Z8k-SDhUHr8AhRDP3rohvF4zPgR_KgfDgBWntA6bEah0v21kyitz4X8365hAGiToJbfqeA5VQ1eZMXwNYZjYz6HodV_aCk7n_yH-TC_RJz9TbxikJC77kG409FG3ACH73VHwmyioul68eWBcRHYDsO-HIWIbHZBoVM7E84SksN7a1fqE_3nYaQgh7izjU41WofDm7AHVyVRt_EmUfYgaeahItdEvhq3j9BH3TOzEzCRY_g0qY0CU4nJK045cq_vwQvBDKyqBwW9fG3f6OtbsNhIR8JT769mkrdd6dIQePfo1ytoSyRv6RAQOWVDOYVbhGWc8hLrQGIPLJF9j5pzDMZSqarLNDFE8LKhOOkv8n2J0NI0iI27n4o4GF2QYWyXxJDOc1qlrtsjne1Ze8Y4hyoiW5Zg5XMr_rTSofJ5n7CkQOOOQHRYov38o6zl1-fyXzqi9STINzdijqpfDeOUQLLAWEykUOcnlBTZHAyufNdMqVDgGaicxx8hEiuSLOHb1szl7vEuNguEsF0lqO6-jUV_wP1pikokDjCvltIJ6ewC3V6gMuQeBGW4jQ23PufHp7ZX06245yYNcYJtYfVQKmP1i00z7HPoXAwZWW29qyPnr7bURhzW_Vz01A9aeETQ3aKJYML650C8Es40f9eZT_X4_7cW781622HiYohyOvcFXSlGl7srmXm8rAFaPraKc1RFZA8D2D80DyMz1rewW0TNLHp8gbO8BsidGMHRWYNO_szMZRCz_iBP-RDqVTewa6TLsfQTm43zDNvsUKvn18k3IdaqyQjwGU47x8iPsetPMBqeZxdHQZX3BAFWChi5aU5q9PuRVKjJCKpfIljKG78hUD1MSZDLMWmdBgUrgPEiXpfp5_QF-jqn2hej9MqPZdufj2Ipe-IfV5a-TeJ0KCtsEh-YpDaU3MfjJGoS5Q12sWVdHacdbNImFhZC-6oqXzl2K0PrTHsOZwB8Eb-Chn3FLHUTbS9L7N9GFha3CtXHScjZ9eoVm17LMQwhFXM1SEJtxz5udkhC2-4ME5-lplJlWpFWoeUL0quq3oLD0dR9JFjkEBxgDJA1p0MhdkTl9L1vCwEQvQ8o4OyIC1A_KDVA6EdACQKxlk26QXqMJqZeYFG0tANaua8PAf25dGHlYLencaCCcEvCwxlZ1dV_fmGjMF6Kx1xZSLNOvrw8QX4M9Ml1gYkvqCBxFm1uidsxwx1v8A5WDW8_alYJ9nyF7RHqOBmGCGEk0vCweg_qR6Eci9Vn0SvaWHYCWnEbcGK0fVEbOA0ar1y5H04mjTaeMiusVu543K4x_1ji130gnuufP329PJy6JggyWyxhfFSQ4K02HTV1_K7rtUC9faYr20wKn-MJyhdzWTXIMpCVYQ-dSYLCdyqHinoosJeizRyiBbvNqeyLT52voQvK2-YzVh9JfTfb0WW4n_jeDEeLFVA7huPx4cQpv-rXfVt7YbBYNkFgV4Aa9pNLvKFJvmtDZhy-iNNXy9Lb8_qUY_WRn57_mO0)

**4.3.5 Mockups de Interfaces Principales**

[Incluya bocetos o mockups de las pantallas principales:]
- Pantalla de login
- Panel principal / Dashboard
- Pantalla de préstamos
- Pantalla de búsqueda de catálogo
- Pantalla de registro de usuario

[Puede usar herramientas como Figma, Balsamiq, o incluso dibujos escaneados]

<br>

### 4.4 Matriz de trazabilidad

<!--
La matriz de trazabilidad vincula requisitos con otros artefactos del proyecto
para asegurar que todos los requisitos están cubiertos en diseño, implementación,
y pruebas.

TIPOS DE TRAZABILIDAD:
- Requisitos <-> Casos de Uso
- Requisitos <-> Casos de Prueba
- Requisitos <-> Módulos de Código
- Requisitos <-> Fuente (stakeholder que lo solicitó)
-->

**4.4.1 Matriz Requisitos - Casos de Uso**

| Requisito | Caso de Uso Relacionado | Prioridad |
|-----------|-------------------------|-----------|
| RF-001 | CU-000 (Login) | Esencial |
| RF-010 | CU-003 (Registrar Usuario) | Esencial |
| RF-030 | CU-001 (Realizar Préstamo) | Esencial |
| RF-031 | CU-001 (Realizar Préstamo) | Esencial |
| RF-040 | CU-002 (Realizar Devolución) | Esencial |
| ... | ... | ... |

**4.4.2 Matriz Requisitos - Casos de Prueba**

| Requisito | Casos de Prueba | Estado Prueba |
|-----------|-----------------|---------------|
| RF-001 | TC-001, TC-002, TC-003 | Pendiente |
| RF-002 | TC-004, TC-005 | Pendiente |
| RF-010 | TC-010, TC-011, TC-012, TC-013 | Pendiente |
| ... | ... | ... |

[Esta matriz se completará durante la fase de pruebas]

<br>


*Plantilla elaborada con propósitos académicos*  
*Basada en IEEE Std 830-1998*  
*Versión  1.0 - Octubre 2025*
