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




#### 3.1.2 Módulo de Gestión de Usuarios (Clientes de la Biblioteca)




---

### 3.2 Requisitos de interfaz eextern

#### 3.2.1 Interfaz de usuario



#### 3.2.2 Interfaz de hardware




#### 3.2.3 Interfaz de software



#### 3.2.4 Interfaz de comunicación


---

### 3.3 Requisitos no funcionales



#### 3.3.1 Rendimiento




#### 3.3.2 FFiabilida



#### 3.3.3 Disponibilidad




#### 3.3.4 Seguridad





#### 3.3.5 Mantenibilidad
`


#### 3.3.6 Portabilidad



---

### 3.4 Requisitos de diseño




---

### 3.5 Requisitos de calidad




---

### 3.6 Restricciones del sistema




---

### 3.7 Atributos del sistema





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
