# Especificación de Requisitos de Software (SRS)
### Proyecto: Unicafe
*Versión [1.0]*

<br>

<img width="445" height="127" alt="image" src="https://github.com/user-attachments/assets/a2cb6e38-e0cb-4149-b56f-a295d28b4a78" />

*24/11/2025*

**Control de Versiones:**

| Versión | Fecha | Autor | Descripción de Cambios |
|---------|-------|-------|------------------------|
| 1.0 | 24/11/2025 | nicolas| Versión final del documento |
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


<br>

---

## 1 INTRODUCCIÓN


═══════════════════════════════════════════════════════════════════════════════
SECCIÓN 1: INTRODUCCIÓN
═══════════════════════════════════════════════════════════════════════════════

### 1.1 Propósito


OBJETIVO DE ESTA SUBSECCIÓN:
Este SRS tiene como objetivo definir los requerimientos del sistema de gestión integrado para UniCafé, enfocado en mejorar el control de acceso, subsidios, inventarios y trazabilidad del consumo.

Está dirigido al equipo de desarrollo y pruebas, a la administración de UniCafé y a los directivos de la UCP, quienes usarán esta información para diseñar, validar y tomar decisiones sobre el sistema.

El documento será la guía base durante el ciclo de vida del proyecto, asegurando alineación entre necesidades, implementación y resultados esperados.

Esta versión se centra en los módulos esenciales del sistema; futuras fases podrán ampliar funcionalidades y nivel de integración.


<br>

### 1.2 Alcance

 
Nombre del Sistema:
Sistema Integrado de Gestión del Restaurante Universitario – SIGRU UniCafé

Descripción:
El SIGRU UniCafé gestionará el control de acceso, la identificación de usuarios con subsidio, el registro de consumos y el inventario alimentario para optimizar la operación del restaurante, reducir pérdidas y mejorar la trazabilidad.

Beneficios Principales:
- Control de subsidios y reducción de fraude.
- Menor desperdicio de alimentos.
- Mayor eficiencia operativa y mejor atención al usuario.

Objetivos Específicos:
- Validar acceso y consumo por usuario.
- Administrar subsidios y su uso.
- Mantener inventarios actualizados y generar reportes.

Límites del Sistema:
- No incluye pagos externos, contabilidad ni gestión avanzada de proveedores.
- La integración con otros sistemas se realizará en fases futuras.

Relación con Otros Sistemas:
Funcionará inicialmente de forma independiente, con posibilidad de integrarse a plataformas institucionales.

<br>

### 1.3 Personal involucrado


OBJETIVO DE ESTA SUBSECCIÓN:

| Nombre                                | Rol                            | Responsabilidades                                 | Información de contacto |
|---------------------------------------|--------------------------------|---------------------------------------------------|-------------------------|
| Administración UniCafé                | Cliente                        | Aprobar requisitos y validar entregas del sistema | admin-unicafe@ucp.edu   |
| Coordinación Proyecto – Ing. Sistemas | Jefe de Proyecto               | Gestionar planificación, comunicación y recursos  | jefeproy-sigru@ucp.edu  |
| Analista del Proyecto                 | Analista de Requisitos         | Documentar y validar requerimientos               | analista.sigru@ucp.edu  |
| Líder Técnico                         | Arquitecto/Líder de Desarrollo | Diseño técnico y supervisión del desarrollo       | devlead.sigru@ucp.edu   |
| Responsable QA                        | Líder de Pruebas               | Garantizar calidad y control de defectos          | qa.sigru@ucp.edu        |




<br>

### 1.4 Definiciones, acrónimos y abreviaturas


OBJETIVO DE ESTA SUBSECCIÓN:



| Término | Definición |
|---------|------------|
| **API** | Interfaz de Programación de Aplicaciones. Permite la comunicación e integración entre sistemas. |
| **COMENSAL** | Usuario final que hace uso del servicio del Restaurante Universitario UniCafé. |
| **CONTROL DE ACCESO** | Validación del derecho del usuario para ingresar y consumir en el restaurante. |
| **CRUD** | Operaciones básicas de datos: Crear, Leer, Actualizar y Eliminar. |
| **INVENTARIO** | Registro y control de los insumos alimentarios del restaurante. |
| **MENÚ** | Planificación de comidas ofrecidas diariamente en UniCafé. |
| **RF** | Requisito Funcional: función específica que el sistema debe cumplir. |
| **RNF** |Requisito No Funcional: características de calidad o restricciones del sistema. |
| **SIGRU UniCafé** | Sistema Integrado de Gestión del Restaurante Universitario UniCafé (software propuesto). |
| **SRS** | Documento de Especificación de Requisitos del Software. |
| **Stakeholder** | Persona o entidad involucrada o afectada por el proyecto. |
| **SUBSIDIO** | Beneficio económico otorgado a ciertos comensales para cubrir parcial o totalmente el costo del alimento. |
| **TRAZABILIDAD** | Registro detallado del consumo y movimientos del sistema para seguimiento y control. |
| **UI** |Interfaz de Usuario: medio visual y funcional para interactuar con el sistema.|
| **UX** | Experiencia del Usuario: percepción general del comensal al utilizar el sistema. |


<br>

### 1.5 Referencias


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


**Estándares y Normas**

1. IEEE Computer Society. (1998). IEEE Recommended Practice for Software Requirements Specifications. IEEE Std 830-1998.

2. ISO/IEC/IEEE 29148:2018. Systems and software engineering — Requirements engineering.

**Documentos del Proyecto**

3. Facultad de Ingeniería UCP. (2025). Visión del Proyecto SIGRU UniCafé. Universidad Católica de Pereira.

4. Facultad de Ingeniería UCP. (2025). Plan de Proyecto SIGRU UniCafé. Universidad Católica de Pereira.

**Documentación Técnica**

5. PostgreSQL Global Development Group. (2024). PostgreSQL Documentation.

6. ReactJS. (2024). React – Official Documentation.

**Bibliografía de Referencia**

7. Sommerville, I. (2016). Ingeniería de Software (10.ª ed.). Pearson.

8. Pressman, R. S., & Maxim, B. R. (2021). Ingeniería del Software: Un Enfoque Práctico (9.ª ed.). McGraw-Hill.

**Recursos en Línea**

9. UCP – Programa de Ingeniería de Sistemas y Telecomunicaciones. (2025). Material académico sobre requisitos de software. Aula virtual UCP.


<br>

### 1.6 Resumen

Este SRS está organizado para facilitar la comprensión del sistema SIGRU UniCafé y sus requerimientos. **La Sección 2** presenta una visión general del sistema, incluyendo el contexto del Restaurante Universitario, las funciones principales, las restricciones, los usuarios involucrados y las dependencias externas. Esta sección ofrece al lector una perspectiva completa del propósito y alcance del software dentro de la operación de UniCafé.

**La Sección 3** contiene la descripción detallada de los requerimientos funcionales y no funcionales del sistema. Aquí se especifican las características del control de acceso, gestión de subsidios, registro de consumos, inventarios, reportes y demás funcionalidades clave. Además, se estructuran prioridades, criterios de aceptación y cualquier restricción técnica necesaria para el desarrollo.

En conjunto, el documento brinda una guía clara y trazable para el diseño, construcción y validación del sistema propuesto, asegurando alineación entre necesidades institucionales y la solución tecnológica planteada.

<br>

---

## 2 DESCRIPCIÓN GENERAL


### 2.1 Perspectiva del producto

Es una aplicación la cual su objetivo es mejorar la atención de los clientes, manejar el consumo y desperdicio de los alimentos y el tema de los subsidios. Estto, mediante un sistema tecnológico eficaz y adecuado, que esta compuesto por turnos en la fila de manera digital, organización del subsidio y manejo de inventario.

- Interfaz con los usuarios (Visualización del menú, turnos y registro)
- Interfaz con los empleados (Gestión del menú, inventario y subsidios)
- Interfaz con el sistema de subsidios (Comprobar el subsidio dependiendo del rol del cliente)
- <img width="714" height="419" alt="image" src="https://github.com/user-attachments/assets/c0fe149e-9cb6-4757-a392-cf93fa6d5890" />


### 2.2 Funciones del producto

 
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

El Sistema UniCafe proporcionará las siguientes funcines principales:

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
  

### 2.3 Características de los usuarios
Comensales: Son aquellos que realizan pedidos en el restaurante
- Manejan dispositivos tecnologicos para realizar pedidos
- Quieren que exista más ordén en las filas
- Desean saber el valor del subsidio
- Quieren conocer el menú que hay
- Requieren notificaciones como de ofertas y descuentos del restaurante

Administrativos y empleados: Son las personas la cuales están encargadas del brindar el servicio
- Conocen los procesos que realizan en el restuarnte
- Necesitan acceso en el sistema, incluyendo los informes
- Buscan el buen manjeo de los alimentos
- Desean obtener soluciones para manejar el consumo y desperdicio de alimentos
- Deben tener permitido la modificación e los procesos, como los turnos de fila, inventario, entre otros.

Técnico en sistemas: Persona o personas encargada de mantener y supervisar el buen funcionamiento del sistema
- Tiene conocimiento acerca del sistema, como lo es la base de datos
- Deben tener permitido el acceso a las actualizaciones
- Garantizan la seguridad de los datos 

| Característica            | Usuario Tipo 1: [Comensales]                                                                                                                                                                                                                          | Usuario Tipo 2: [Administrativos y empleados]                                                                                                                                                                                                                                                                                            | Usuario Tipo 3: [Técnico en sistemas                                                                                                                                |
|---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Descripción               | Son aquellos que realizan pedidos en el restaurante                                                                                                                                                                                                   | Son las personas las cuales están encargadas del brindar el servicio                                                                                                                                                                                                                                                                     | Persona o personas encargadas de mantener y supervisar el buen funcionamiento del sistema.                                                                          |
| Responsabilidades         | - Manejan dispositivos tecnológicos para realizar pedidos - Quieren que exista más orden en las filas - Desean saber el valor del descuento - Quieren conocer el menú que hay - Requieren notificaciones como de ofertas y descuentos del restaurante | - Conocen los procesos que realizan en el restaurante - Necesitan acceso al sistema, incluyendo los informes - Buscan el buen manejo de los alimentos - Desean obtener soluciones para manejar el consumo y el desperdicio de alimentos - Deben tener permitido modificar los procesos, como los turnos de fila, inventario, entre otros | - Tiene conocimiento acerca del sistema, como lo es la base de datos - Deben tener permitido el acceso a las actualizaciones - Garantizan la seguridad de los datos |
| Nivel Técnico             | Medio                                                                                                                                                                                                                                                 | Medio                                                                                                                                                                                                                                                                                                                                    | Alto                                                                                                                                                                |
| Experiencia en el Dominio | Novato                                                                                                                                                                                                                                                | Experto                                                                                                                                                                                                                                                                                                                                  | Experto                                                                                                                                                             |
| Frecuencia de uso         | Diaria                                                                                                                                                                                                                                                | Diaria                                                                                                                                                                                                                                                                                                                                   | Diaria                                                                                                                                                              |
| Funciones Principales     | - Consulta el menú del día en línea - Consulta el valor del almuerzo según su categoría. - Ingresa al comedor con carnet/identificación - Recibe servicio en línea buffet                                                                             | - Valida la identidad del comensal (escaneo de carnet) - Identifica la categoría (estudiante becado, regular, docente, externo) - Cobra según la tarifa correspondiente3. - Controla porciones servidas (estandarización) - Calcula las cantidades de producción según la demanda histórica                                              | - Realizar el mantenimiento del sistema - Actualiza según las indicaciones - Verifica que todo esta funcionando de manera adecuada                                  |



<br>

### 2.4 Restricciones

# Restricciones Técnicas

- El sistema solo puede funcionar dentro de la infraestructura tecnológica disponible en el restaurante.

- El sistema debe operar exclusivamente dentro del horario establecido por el restaurante; fuera de este horario no se garantizará disponibilidad total.

- La asignación de turnos debe realizarse automáticamente; los empleados no pueden modificarla manualmente.

- El sistema depende de una conexión estable a Internet o red local; no puede operar correctamente sin ella.

- La base de datos debe permanecer en un entorno seguro que cumpla con las normas de seguridad informática definidas por el restaurante.

- El técnico solo puede intervenir en tareas de mantenimiento, actualizaciones y seguridad; no puede modificar procesos operativos.
 
# Restricciones Operativas

- Los empleados tienen la responsabilidad obligatoria de registrar todas las ventas; el sistema no puede hacerlo de forma automática sin intervención humana.

- Solo empleados autorizados pueden modificar procesos, datos sensibles o configuraciones administrativas.

- El sistema debe respetar la capacidad real del restaurante para asignar turnos; no puede exceder el aforo permitido.

- Los comensales solo pueden acceder a funciones destinadas específicamente para clientes (menú, turnos, pedidos, subsidios).

- El sistema no puede otorgar subsidios sin validación previa del módulo correspondiente.

# Restricciones de Seguridad

- El sistema debe evitar el acceso de usuarios sin permisos a información de inventario, informes, subsidios y datos internos.

- La información del comensal y de los empleados debe manejarse conforme a las políticas de privacidad del restaurante.

- El técnico no puede acceder a información personal de comensales o empleados que no sea necesaria para mantenimiento técnico.

# Restricciones de Dependencias

- El funcionamiento del módulo de usuarios depende de la verificación correcta del comensal y su subsidio.

- El módulo de notificaciones depende de la información generada en el módulo de turnos y los niveles de suministro.

- El módulo de pedidos depende del inventario actualizado y del turno asignado.

- El módulo de menú depende de la información actualizada de platos, ofertas y descuentos; sin actualización, puede mostrar datos incorrectos.

- La operación del sistema depende del personal capacitado para utilizar correctamente las funciones asignadas a cada rol.

### 2.5 Suposiciones y dependencias

**Suposiciones:**

Comensal
- Se asume que el comensal cuenta con dispositivos electronicos para utilizar la aplicacion
- Se sume que los clientes pueden comprender los turnos, precios, entre otros.

Empleados
- Se asume que los empleados conocen acerca del sistema
- Se asume que personas especificas tienen permisos para modificar procesos del restaurante

Técnico
- Se asume qu el técnico posee conocmientos acerca de bases de datos, servidores y seguridad digital
- Sea  sume quue es responsable de las actualizaciones del sistema
- Se asume que no interviene en procesos operativos del restaurante

- El sistema funciona en los horarios establecidos en el restaurante
- Los turnos se asignan automaticamente
- Los empleados tienen la responsabilidad de registrar las ventas
- La base de datos esta segura y protegida mediante seguridad informatica
- El restaurante tiene infraestructura tecnologica para la aplicación 

**Dependencias:**

Sistema
Modelo Usuarios: Identificar el comensal y su subsidio
Modulo Notificaciones: Revisar turno y alertas de suministros
Modulo pedidos: Revisar turno e inventario
Modelo de Menú: Información de los platos, ofertas y descuentos

Cliente
- Modulo de menú
- Modulo Turnos
- Modulo pedidos
- Modulo subsidios
- Modulo notificaciones (turno)

Empleados
- Modulo inventario
- Modulo Informes
- Modulo Turnos
- Modulo Mneú
- Modulo Subsidios
  
### 2.6 Requisitos futuros

 # Clientes

- El sistema podría integrar métodos biométricos (huella, QR dinámico o reconocimiento facial) para identificar al comensal y validar subsidios.

- Se podrá incorporar un historial de consumo para permitir recomendaciones personalizadas de menú.

- Se añadirá la posibilidad de que los comensales califiquen los platos o el servicio dentro de la aplicación

  # Turnos

- El sistema deberá permitir ajustar automáticamente la asignación de turnos en función de la demanda histórica.

- Se podrá implementar un sistema de predicción de afluencia que sugiera horarios óptimos al comensal.

- El módulo de turnos podría integrarse con sensores físicos (por ejemplo, contadores de personas) para validar asistencia real.
- 
  # Pedidos

- Los pedidos podrán automatizarse mediante asistentes virtuales o chatbots internos.

- Se podrá permitir pedidos programados para fechas u horarios específicos.

- El sistema podría integrar pagos digitales o billeteras electrónicas desde la aplicación del comensal.

  # Subsidios

- Se podrá integrar la verificación automática del subsidio con sistemas externos institucionales o gubernamentales.

- El sistema permitirá la gestión de múltiples tipos de subsidios y reglas avanzadas de elegibilidad.

- Se añadirá un módulo predictivo para estimar el uso futuro de subsidios por comensal.

  # Empleados

- El sistema permitirá crear perfiles avanzados de roles con permisos personalizados.

- El módulo de informes podrá generar dashboards dinámicos con IA para análisis de ventas y stock.

- Se podrán validar asistencias del personal mediante huella, QR o geolocalización interna.
  
  

---

## 3 REQUISITOS ESPECÍFICOS


### 3.1 Requisitos funcionales


═══════════════════════════════════════════════════════════════════════════════
REQUISITOS FUNCIONALES
═══════════════════════════════════════════════════════════════════════════════
**Usuarios**
| ID                      | RFU-01                                                                                                                                         |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Visualizacion del menu                                                                                                                         |
| Descripcion             | El sistema debe permitir al usuario ver el menu diario, donde se evidencia el nombre, los ingredientes y el precio.                            |
| Prioridad               | Esencial                                                                                                                                       |
| Estabilidad             | Alta                                                                                                                                           |
| Fuente                  | Cliente/Comensal                                                                                                                               |
| Criterios de Aceptacion | 1. El cliente puede ver el menu, sin inciar sesion 2. Los datos coinciden con la informacion de la base de datos 3. El menu se va actualizando |
| Dependencias            | RFE-02 (Gestion del menu)                                                                                                                      |
| Comentarios             | Se puede acceder en dispositivos moviles                                                                                                       |

| ID                      | RFU-05                                                                                                                           |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Generacion de turno digital                                                                                                      |
| Descripcion             | El sistema debe generar un turno digital para cada usuario que va a comprar, asignando un numero secuencial.                     |
| Prioridad               | Esencial                                                                                                                         |
| Estabilidad             | Alta                                                                                                                             |
| Fuente                  | Empleado atenciòn al cliente                                                                                                     |
| Criterios de Aceptacion | 1. Se asigna un turno para usuario 2. El turno aparece en la lista 3. El tiempo estimado se actualiza segùn el flujo de atenciòn |
| Dependencias            | Ninguna                                                                                                                          |
| Comentarios             | Puede integrarse con notificaciones push                                                                                         |

| ID                      | RFU-08                                                                                                                            |
|-------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Consultar subsidio                                                                                                                |
| Descripcion             | El sistema debe mostrar al cliente el subsidio con el que cuenta antes de realizar la compra                                      |
| Prioridad               | Esencial                                                                                                                          |
| Estabilidad             | Media                                                                                                                             |
| Fuente                  | Cliente/Administraciòn                                                                                                            |
| Criterios de Aceptacion | 1. La informaciòn del subsidio se obtiene correctamente 2. Se actualiza automaticamente 3. El usuario recibe la informacion clara |
| Dependencias            | RFS-02 (El usaurio debe verificar)                                                                                                |
| Comentarios             | Importante para evitar errores                                                                                                    |


| ID                      | RFU-10                                                                                                                                                  |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Reservade comidad                                                                                                                                       |
| Descripcion             | El sistema permite al cliente reservar platos con anticipacion dentro de un determinado horario                                                         |
| Prioridad               | Deseable                                                                                                                                                |
| Estabilidad             | Media                                                                                                                                                   |
| Fuente                  | Cliente/Empleado                                                                                                                                        |
| Criterios de Aceptacion | 1. Lareserva se registra correctamente 2. El sistema bloquea cuando hay cupos agotados 3. S emite una confirmacion medinate algun medio de comunicacion |
| Dependencias            | RFU-01 (Visualizacion del menu), REF-07 (Inventario)                                                                                                    |
| Comentarios             | Reducir filas                                                                                                                                           |

| ID                      | RFU-15                                                                                                                               |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Notificaciones personalizadas                                                                                                        |
| Descripcion             | El sistema debe enviar notificaciones automaticas al usuario a cerca de su turno y subsidio                                          |
| Prioridad               | Deseable                                                                                                                             |
| Estabilidad             | Alta                                                                                                                                 |
| Fuente                  | Usuario/Administrador                                                                                                                |
| Criterios de Aceptacion | 1.  El usuario recibe notificaciones oportunas 2. Los mensajes contienen informacion correcta 3. Puede desactivar las notificaciones |
| Dependencias            | RFU-05(Turnos), RFS-10(Subsidio agotado)                                                                                             |
| Comentarios             | Puede usarse para promociones                                                                                                        |


**Empleados**
| ID                      | RFE-02                                                                                                                                                                 |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Gestion del menu                                                                                                                                                       |
| Descripcion             | El sistema debe permitir al empleado editar los platos del menù                                                                                                        |
| Prioridad               | Esencial                                                                                                                                                               |
| Estabilidad             | Alta                                                                                                                                                                   |
| Fuente                  | Administrador/Chef                                                                                                                                                     |
| Criterios de Aceptacion | 1. Se pueden crear y editar platos correctamente 2. Los cambios se reflejan en la interfaz del usuario 3. Se evita que la eliminaciòn de platos que se estan comprando |
| Dependencias            | RFU-01 (Ver el menu)                                                                                                                                                   |
| Comentarios             | Puede incluir imagenes del plato                                                                                                                                       |

| ID                      | RFE-07                                                                                                                                                               |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Gestion del inventario                                                                                                                                               |
| Descripcion             | El sistema debe permitir a los empleados registrar entradas y salidas de los ingredientes y platos, actualizando el inventario.                                      |
| Prioridad               | Esencial                                                                                                                                                             |
| Estabilidad             | Alta                                                                                                                                                                 |
| Fuente                  | Chef/Adminsitraciòn                                                                                                                                                  |
| Criterios de Aceptacion | 1. Las salidas del inevntario se registran con cada venta que se realiza 2. El stock no debe ser negativo 3. El sistema genera alarmar cunado ese bajo el inventario |
| Dependencias            | RFU-04 (Registro de ventas)                                                                                                                                          |
| Comentarios             | Mediante reportes automaticos                                                                                                                                        |


| ID                      | RFE-10                                                                                                                                             |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Control de desperdicios                                                                                                                            |
| Descripcion             | El sistema debe permitir registrar alimentos desperdiciados, que incluya el motivo, cantidad y precio                                              |
| Prioridad               | Deseable                                                                                                                                           |
| Estabilidad             | Alta                                                                                                                                               |
| Fuente                  | Chef/Empleado                                                                                                                                      |
| Criterios de Aceptacion | 1. Se pueden registrar desperdicios con motivo 2. Los datos se reflejan en los reportes de consumo 3. Permite filtrar por fecha o tipo de alimento |
| Dependencias            | RFE-07(Inventario)                                                                                                                                 |
| Comentarios             | Util para auditorias y manejo de costos                                                                                                            |

| ID                      | RFE-16                                                                                                                                         |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Cierre de caja                                                                                                                                 |
| Descripcion             | El sistema permitira genere un resumen del total de ventas, subsidios y medios de pago obtenidos                                               |
| Prioridad               | Esencial                                                                                                                                       |
| Estabilidad             | Alta                                                                                                                                           |
| Fuente                  | Administrador                                                                                                                                  |
| Criterios de Aceptacion | 1. Los totales coinciden con las transacciones registradas 2. Se puede exportar en PDF 3. Se guarda una copia de seguridad en la base de datos |
| Dependencias            | RFE-04 (Registro de consumo), RFS-04 (Subsidios)                                                                                               |
| Comentarios             | Mejora la trasparencia y control contable                                                                                                      |


**Subsidios**
| ID                      | RFE-02                                                                                                                                                           |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Verificacion del cliente                                                                                                                                         |
| Descripcion             | El sistema debe verificar el rol del cliente mediante la base de datos, para saber el valor del subsidio                                                         |
| Prioridad               | Esencial                                                                                                                                                         |
| Estabilidad             | Media                                                                                                                                                            |
| Fuente                  | Empleado                                                                                                                                                         |
| Criterios de Aceptacion | 1. El rol se valida mediante el inicio de sesion 2. Se aplican las reglas de subsidio  3. Los usuarios que no forman parte de la institucion no reciben subsidio |
| Dependencias            | RFU-08 (Consultar subsidios)                                                                                                                                     |
| Comentarios             | Mantener buena conexion con la base de datos                                                                                                                     |


| ID                      | RFE-06                                                                                                                                 |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Reporte de subsidios                                                                                                                   |
| Descripcion             | El sistema debe generar reportes periodicos del uso de subsidios                                                                       |
| Prioridad               | Deseable                                                                                                                               |
| Estabilidad             | Alta                                                                                                                                   |
| Fuente                  | Contador                                                                                                                               |
| Criterios de Aceptacion | 1. Se puede exportar el reporte en PDF 2. El valor coincide con los registros del sistema 3. Los datos se agrupan por usuario y fecha  |
| Dependencias            | RFU-04 (Registro de subsidios)                                                                                                         |
| Comentarios             | Control de presupuestos de la empresa                                                                                                  |

**Requisitos trasversales**
| ID                      | RFE-06                                                                                                                                                             |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nombre                  | Sincronizaciòn de datos                                                                                                                                            |
| Descripcion             | El sistema debe sincronizar en tiempo real la informacion del cliente, el subsidio y el empleado                                                                   |
| Prioridad               | Esencial                                                                                                                                                           |
| Estabilidad             | Alta                                                                                                                                                               |
| Fuente                  | Tecnico                                                                                                                                                            |
| Criterios de Aceptacion | 1. Las actualizacion se deden evidenciar en el menor tiempo posible 2. No existen datos que este desincronizados 3. Las actualizaciones se registran en el sistema |
| Dependencias            | Todas las interfaces                                                                                                                                               |
| Comentarios             | Requiere conectividad estable                                                                                                                                      |

| ID                      | RFS-07                                                                                                      |
|-------------------------|-------------------------------------------------------------------------------------------------------------|
| Nombre                  | Validacion del limite del subsidio                                                                          |
| Descripcion             | El sistema controlara que el usuario no exceda el numero de subsidios permitidos                            |
| Prioridad               | Esencial                                                                                                    |
| Estabilidad             | Alta                                                                                                        |
| Fuente                  | Contador                                                                                                    |
| Criterios de Aceptacion | 1. No se puede superar el limite del subsidio 2. El sistema muestra un aviso 3. Los datos reflejan reportes |
| Dependencias            | RFS-02(Verificacion rol)                                                                                    |
| Comentarios             | Optimiza recursos                                                                                           |


#### 3.1.1 Módulo de Autenticación y Seguridad


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



---

### 3.2 Requisitos de interfaz eextern

#### 3.2.1 Interfaz de usuario

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



<br>

#### 3.2.2 Interfaz de hardware


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

<br>

#### 3.2.4 Interfaz de comunicación


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


<br>

---

### 3.3 Requisitos no funcionales



#### 3.3.1 Rendimiento


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

#### 3.3.2 FFiabilida

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

**RNFD-005: Degradación controlada**

Si servicios externos (Sistema Municipal, servidor SMTP) no están disponibles, el sistema DEBE continuar operando con funcionalidad reducida en lugar de fallar completamente:

- Si SMI no está disponible: Permitir registro manual sin validación automática
- Si SMTP no está disponible: Encolar correos para envío posterior

El sistema DEBE informar al usuario cuando opera en "modo degradado" sin alarmar innecesariamente.

<br>

#### 3.3.4 Seguridad



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
`
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


**RNFP-001: Independencia de sistema operativo del servidor**

El sistema DEBE poder ejecutarse en servidores Linux (Ubuntu 20.04+, Debian 10+, CentOS 8+) sin modificaciones.

El sistema PUEDE ser compatible con otros sistemas operativos (Windows Server, macOS) pero esto NO es un requisito esencial.

**RNFP-002: Compatibilidad de base de datos**

Aunque el sistema usará PostgreSQL en producción (ver restricción RSW-003), el código DEBE estructurarse de forma que migrar a otro RDBMS (MySQL, MariaDB) requiera cambios mínimos.

Esto se logra usando:
- ORM (Object-Relational Mapping) que abstrae el motor de BD
- Evitar queries SQL específicas de PostgreSQL (a menos que sean críticas para rendimiento)

**RNFP-003: Contenedorización (Deseable)**


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


Ver Sección 2.4 para restricciones completas del sistema. Las restricciones principales son:

- Restricciones tecnológicas: Servidores Linux existentes, PostgreSQL como BD
- Restricciones de integración: API del Sistema Municipal de Identificación v2.1
- Restricciones presupuestarias: Máximo $25,000 USD
- Restricciones de tiempo: Implementación en 6 meses
- Restricciones de personal: Equipo de 4 personas
- Restricciones regulatorias: Cumplimiento de Ley de Protección de Datos Personales


<br>

---

### 3.7 Atributos del sistema



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



### 4.1 Modelos de casos de uso



**Lista de Casos de Uso del Sistema:**

- **CU-001**: Mirar menu
- **CU-002**: Pagar cuenta
- **CU-003**: Registrar carnet
- **CU-004**: Hacer pedido
- **CU-005**: Añadir menu semanal

**CU-001: Resturante unicafe**

| Campo | Descripción |
|-------|-------------|
| *ID* | CU-001 |
| *Nombre* | mirar menu|
| *Actores* | Usuario del restaurante (primario) |
| *Descripción* | permite al usuario visualizar el menú semanal, para posteriormente realizar tareas como hacer pedido|
| *Precondiciones* | 1. Al usuario se le válido el carnet<br>2. El usuario NO está suspendido ni tiene multas |
| *Postcondiciones* | 1. La página debe redirigir al usuario a una nueva pagina<br>2. la nueva página debe contener el menú semanal  |
| *Flujo Principal* | 1. El sistema solicita identificarse,mediante un carnet<br>2. El usuario escanea su carnet <br>3. el sistema valida el carnet<br>4. El usuario escanea el código QR<br>5. El sistema redirige al usuario a una nueva pestańa <br>6. El usuario visualiza el menú semanal<br>7. El usuario hace su pedido |
| *Flujos Alternativos* | *4a. carnet no valido:<br>  4a1. El sistema muestra mensaje "carted invalido"<br>  4a2. El sistema ofrece opción "llamar su soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br>7a. error en la pagina*:<br>  7a1.  El sistema nuestra un mensaje "error"<br>  7a2. Si esto sucede, el sistema ofrece opción "reportar problema"<br>  7a3. un usuario de soporte será alertado <bro> 7a4. se soluciona el problema |
| *Flujos de Excepción* | *5a. Usuario suspendido o con multas vencidas*:<br>  5a1. El sistema muestra advertencia "Usuario suspendido" o "Usuario tiene multas vencidas por $[monto]"<br>  5a2. El sistema NO permite continuar con la venta<br>  5a3. Fin del caso de uso<br>  |
| *Requisitos Relacionados* | CU-01 (visualizar menu)<br>CU-02 (Escanear QR)<br>CU-03 (consulta menú semanal) |
<br>

**CU-003: Pagar cuenta**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-002 |
| **Nombre** | pagar cuenta|
| **Actores** | cajero (primario), Usuario del restaurante (secundario) |
| **Descripción** | permite al carejo realizar el pago de los productos consumidos por el usuario|
| **Precondiciones** | 1. se validan los productos pedidos por el usuario <br>2. se le escanea el carnet al usuario<br>3. se crea la factura <br>4. se le cobra lo correspondiente al usuario |
| **Postcondiciones** | 1. el sistema debe tener registrado los productos pedidos por el usuario <br>2. el sistema debe hacer la suma de los precios de los productos vendidos<br>3. el sistema debe crear una factura <br>4. el sistema debe guardar una copia de la factura en la base de datos y imprimir una fisica
| **Flujo Principal** | 1. se validan los productos pedidos por el usuario <br>2. se le escanea el carnet, para validar su rol y ańadirle su descuento correspondiente (si se puede) <br>3. se crea la factura <br>4. se imprime una copia de la factura <br>5.se le cobra lo correspondiente al usuario |
| **Flujos Alternativos** | **4a. compra no registrada**:<br>  4a1. El sistema muestra mensaje "compra no registrada"<br>  4a2. El sistema ofrece opción " sa soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br>**7a. error en la pagina**:<br>  7a1.  El sistema nuestra un mensaje "error"<br>  7a2. Si esto sucede, el sistema ofrece opción "reportar problema"<br>  7a3. un usuario de soporte será alertado <bro> 7a4. se soluciona el problema |
| **Flujos de Excepción** | **5a. Usuario suspendido o con multas vencidas**:<br>  5a1. El sistema muestra advertencia "Usuario suspendido" o "Usuario tiene multas vencidas por $[monto]"<br>  5a2. El sistema NO permite continuar con la venta<br>  5a3. Fin del caso de uso<br>  |
| **Requisitos Relacionados** | CO-01 (pagar cuenta)<br>CO-02 (validar carnet)<br>CO-03 (aplicar descuento)<br>CO-04 (generar factura)|
<br>

**CU-003: Registrar carnet**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-003 |
| **Nombre** | Registrar carnet|
| **Actores** | administrador (primario) |
| **Descripción** | Permite al usuario ańadir toda la información correspondiente a un carnet |
| **Precondiciones** | 1. identificar usuario<br>2. verificar datos <br>3. crear nuevo usuario |
| **Postcondiciones** | 1. el sistema debe permitir crear un nuevo usuario <br>2. añadir los datos en el nuevo usuario <br>3. el sistema debe verificar que no falte informacion<br>4. el nuevo usuario debe quedar dentro de la base de datos  |
| **Flujo Principal** | 1. el sistema empieza a crear el carnet<br>2. el administrador introducira la informacion nesesaria (nombre, apellidos, rol, estado, etc) <br>3. se verificara el rol del usuario<br>4. en caso tal de tener un rol que posea algun descuento, se le aplicara al carnet <br>5. el administrador finalizara la creacion del usuario  |
| **Flujos Alternativos** | **4a. datos faltantes**:<br>  4a1. El sistema muestra mensaje "datos faltantes"<br>  4a2. El sistema pondra en rojo los espacios con informacion faltante <br>  4a3. en caso tal de no poder o no querer seguir creando el usuario, se podra cancelar el proceso<br><br>**7a. datos duplicados**:<br>  7a1.  El sistema nuestra un mensaje "datos duplicados"<br>  7a2. Si esto sucede el sistema informara con el color rojo el campo donde sucede este echo<br>  7a3. si esta informacion es erronea, se cancelara el proceso de "creacion de usuario" |
| **Flujos de Excepción** | **5a. informacion erronea**:<br>  5a1. si el sistmea detecta datos duplicados informara de una cituacion  de "informacion erronea"<br>  5a2. el sistema ofrecera llamar al usuario <br>  5a3. si el usurio no quiere llamar al usuario se finalizara  <br>  5a4. el proceso Fin del caso de uso<br>  |
| **Requisitos Relacionados** | CU-01 (registrar usuario)<br>CU-02 (validar carnet) |
<br>

**CU-004: Hacer pedido**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-004 |
| **Nombre** | Hacer pedido|
| **Actores** | usuario del restaurante (primario) |
| **Descripción** | permite al usuario realizar un pedido con los productos que se encuentren en el catálogo del menu|
| **Precondiciones** | 1. el usuario entra a la pagina<br>2. mira el menu <br>3. realiza el pedido |
| **Postcondiciones** | 1. la pagina debe mostrar el menu <br>2. los productos pedidos deben quedar registrados <br>3. el sistema debe registrar el pedido  |
| **Flujo Principal** | 1. el usuario visualizara el menu<br>2. el usuario ira pidiendo los productos que quiere y añadiendolos al carrito <br>3. el sistema mostrara el total del pedido en la pestaña "carrito" <br>4. se le creara un comprobante de la compra  |
| **Flujos Alternativos** | **4a. compra no registrada**:<br>  4a1. El sistema muestra mensaje "compra no registrada"<br>  4a2. El sistema ofrece opción "llamar a soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br>**7a. error en la pagina**:<br>  7a1.  El sistema nuestra un mensaje "error"<br>  7a2. Si esto sucede, el sistema ofrece opción "reportar problema"<br>  7a3. un usuario de soporte será alertado <bro> 7a4. se soluciona el problema |
| **Flujos de Excepción** | **5a.producto agotado**:<br>  5a1. El sistema muestra el mensaje "producto agotado" <br>  5a2. el sistema redirigira al usuario a la pesataña menu <br>  5a3. Fin del caso de uso<br>  |
| **Requisitos Relacionados** | CU-01 (Hacer pedido)<br>CU-02 (Resive el servicio solicitado )<br>CU-03 (Evalua el servicio y el menu)<br>CU-04 (ingresar, identificado por el carnet)<br>CU-05 (Realiza el pago)<br>CU-06 (verificar menu y precio) |
<br>

**CU-005: Registrar venta**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-005 |
| **Nombre** | Registrar venta|
| **Actores** | contador (primario), cajero (secundario)|
| **Descripción** | permite al cajero, registrar los productos vendido en la base de datos para que el contador administre que no exista algun inconeniente |
| **Precondiciones** | 1.el cajero registra la venta<br>2. el contador visualiza las ventas diarias <br>3. el contador crea un informa sobre inconvenientes o valida la informacion|
| **Postcondiciones** | 1. la pagina registra la venta en la base de datos <br>2. el sistema muestra las ventas diarias |
| **Flujo Principal** | 1.el cajero registra la venta <br>2. se crea una factura, tanto virtual como fisica <br>3.el contador entra en el registro de ventas diarias<br>4. en caso de algun inconveniente, se le informara al administrador |
| **Flujos Alternativos** | **4a. producto inexistente**:<br>  4a1. El sistema muestra mensaje "producto inexistente"<br>  4a2. El sistema ofrece opción "llamar su soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br> |
| **Flujos de Excepción** | **5a. Usuario suspendido o con multas vencidas**:<br>  5a1. El sistema muestra advertencia "Usuario suspendido" o "Usuario tiene multas vencidas por $[monto]"<br>  5a2. El sistema NO permite continuar con la venta<br>  5a3. Fin del caso de uso<br>  |
| **Requisitos Relacionados** | CU-01 (Registrar venta)<br>CU-02 (Gestionar metodo de pago)<br>CU-03 (Porcesar valor total)<br>CU-04 (Incorporar ventas en el sistema) |
<br>                                                                                                                                                                                                                                                                                                                                                
**CU-006: Añadir menu semanal**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-006 |
| **Nombre** | Añadir menu semanal|
| **Actores** | chef (primario)|
| **Descripción** | permite al cocinero actualizar, ańadir o eliminar productos que se encuentren en el menu|
| **Precondiciones** | 1. el chef verifica productos en stock<br>2. el chef crea un menu <br>3. el cheft agrega el nuevo menu a la base de datos|
| **Postcondiciones** | 1. la pagina dejara visualizar el inventario actual<br>2. el sistema permitira añadir el nuevo menu semanal  |
| **Flujo Principal** | 1.el chef visualizara el inventario actual <br>2. dependiendo de la cantidad de los productos en stok creara un nuevo menu <br>3. el chef agregara rl nuevo menu en la base de datos<br>4. el sistema verificara que no falte informacion <br>5. el sistema validara el nuevo menu semanal |
| **Flujos Alternativos** | **4a. producto inexistente**:<br>  4a1. El sistema muestra mensaje "producto inexistente"<br>  4a2. El sistema ofrece opción "llamar su soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br>**7a. producto faltante**:<br>  7a1.  El sistema nuestra un mensaje "producto faltante"<br>  7a2. Si esto sucede el sistema informara con el color rojo el campo donde sucede este echo<br>  7a3. si esta informacion es erronea, se cancelara el proceso de "creacion de usuario" |
| **Flujos de Excepción** | **5a. Usuario suspendido o con multas vencidas**:<br>  5a1. El sistema muestra advertencia "Usuario suspendido" o "Usuario tiene multas vencidas por $[monto]"<br>  5a2. El sistema NO permite continuar con la venta<br>  5a3. Fin del caso de uso<br>  |
| **Requisitos Relacionados** | CU-01 (Añadir menu semanal)<br>CU-02 (identidicar cantidades)<br>CU-03 (analiza ingredientes para el menu)<br>CU-04 (segun los ingrdientes, se adapta al menu) |
<br> 

**CU-007: inventario diario**

| Campo | Descripción |
|-------|-------------|
| **ID** | CU-007 |
| **Nombre** | inventario diario|
| **Actores** | Coordinador Operativo (primario)|
| **Descripción** | Permite al Coordinador Operativo, registrar el conteo del inventario diariamente|
| **Precondiciones** | 1. EL Coordinador Operativo hace el conteo del inventario<br>2. El Coordinador Operativo actualiza el inventario|
| **Postcondiciones** | 1. la pagina deja modificar el inventrio actual<br>2. el sistema valida la informacion nueva  |
| **Flujo Principal** | 1. EL Coordinador Operativo hace el conteo del inventario<br>2. el Cordinador Operativo valida su identidad<br>3. El Coordinador Operativo  se registra datos como la cantidad<br>4. la pagina registra la nueva informacion |
| **Flujos Alternativos** | **4a. producto inexistente**:<br>  4a1. El sistema muestra mensaje "producto inexistente"<br>  4a2. El sistema ofrece opción "llamar su soporte"<br>  4a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  4a4. Si el usuario cancela, volver al paso 2<br><br>**7a. producto faltante**:<br>  7a1.  El sistema nuestra un mensaje "producto faltante"<br>  7a2. Si esto sucede el sistema informara con el color rojo el campo donde sucede este echo<br>  7a3. si esta informacion es erronea, se cancelara el proceso de "creacion de usuario"<br><br>**7a. cantidad invalida**:<br>  7a1. El sistema nuestra un mensaje "cantidad invalida"<br>  7a2. algun campo de "cantidad" quedo vacio <br>  7a2. El sistema ofrece opción "llamar su soporte"<br>  7a3. Si el usuario selecciona llamar, ir a (llamar a soporte)<br>  7a4. Si el usuario cancela, volver al paso 2|
| **Flujos de Excepción** | **5a. Usuario no valido**:<br>  5a1. El sistema muestra advertencia "Usuario no valido" <br>  5a2. El sistema NO permite continuar con el registro<br>  5a3. Fin del caso de uso<br>  |
| **Requisitos Relacionados** | CU-01 (inventario diario)<br>CU-02 (Identificar productos que se requieren)<br>CU-03 (Notificar a los proveedores)<br>CU-04 (Analizar los distintos tipos de menu)<br>CU-05 (Determinar los productos faltantes)|
<br> 


### 4.2 Glosario

**Términos Adicionales del Dominio Bibliotecario:**

| Término | Definición |
|---------|------------|
| **Catálogo bibliográfico** | Registro organizado de todos los materiales disponibles en la cafeteria, con información descriptiva de cada uno. |
| **Clasificación Dewey** | Sistema Dewey de clasificación decimal utilizado para organizar alimentos por temas. Rango de 000 a 999. |
| **ISBN** | International Standard Book Number. Código único de 13 dígitos que identifica alimentos comerciales. |
| **MARC** | MAchine-Readable Cataloging. Formato estándar para representar y comunicar información bibliográfica en forma legible por computadora. |
| **Morosidad** | Estado de un usuario con multas en la fecha establecida. |
| **Obra** | Contenido intelectual (ej: "empanadas"). pueden tener variedad de tipos. |
| **Política de préstamo** | Reglas que definen cuántos materiales puede pedir por cada tipo de usuario, por cuántos días, y si puede renovar. |
<br>

### 4.3 Diagramas del sistema


**Modelo 1**

<img width="830" height="371" alt="image" src="https://github.com/user-attachments/assets/b2bb24f7-0e83-4a6c-9f2b-5edffd7bdb77" />

**Modelo 2**

<img width="800" height="391" alt="image" src="https://github.com/user-attachments/assets/766d8192-1541-4734-b22d-188ea506bce1" />

**Modelo 3**

<img width="680" height="461" alt="image" src="https://github.com/user-attachments/assets/3be718c2-2213-4a1c-a6ab-d6f145f0e717" />

**Modelo 4**

<img width="934" height="333" alt="image" src="https://github.com/user-attachments/assets/84323015-e7d0-4a5d-8754-8524bd04979e" />

**Modelo 5**

<img width="1013" height="419" alt="image" src="https://github.com/user-attachments/assets/fec03dc3-6d39-4f21-a1ed-183af78e88c8" />

**Modelo 6**

<img width="1062" height="424" alt="image" src="https://github.com/user-attachments/assets/6278a6cf-7a84-4f88-9d24-64f5ba6c52d6" />

**Modelo 7**

<img width="1039" height="416" alt="image" src="https://github.com/user-attachments/assets/59163192-855a-454b-8daa-9fadf426052e" />
