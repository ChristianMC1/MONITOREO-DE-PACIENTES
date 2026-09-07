# Project Brief — Sistema Web de Monitoreo de Pacientes Universitarios

> **Grupo:** CODYS_DEV  
> **Cliente / Patrocinador:** Área de Bienestar Universitario — Universidad Peruana Unión  
> **Tipo de solución:** Plataforma web institucional  
> **Fecha base del brief:** 30 de agosto de 2026  
> **Actualización documental:** 7 de septiembre de 2026  

---

## 1. Información general

### 1.1 Nombre del proyecto

**Sistema Web de Monitoreo de Pacientes Universitarios**

### 1.2 Cliente / Patrocinador

**Área de Bienestar Universitario de la Universidad Peruana Unión (UPEU).**

### 1.3 Descripción breve

El Sistema Web de Monitoreo de Pacientes Universitarios es una plataforma orientada al registro, seguimiento y monitoreo de estudiantes que requieren atención médica, psicológica o acompañamiento institucional.

Su finalidad es centralizar la información de cada estudiante, registrar las atenciones realizadas, controlar el seguimiento de los casos, gestionar derivaciones entre áreas, identificar situaciones prioritarias, generar alertas y conservar un historial trazable de las acciones realizadas.

El sistema busca mejorar la coordinación entre Bienestar Universitario y las áreas responsables del acompañamiento del estudiante, reduciendo la dependencia de registros dispersos o físicos.

---

# 2. Antecedentes y problema

Actualmente, parte de la información relacionada con estudiantes que presentan problemas de salud, hospitalizaciones, traumas, situaciones psicológicas u otras necesidades de acompañamiento puede encontrarse distribuida entre distintas áreas o registrada de forma manual.

Esta situación dificulta:

- Conocer el estado actualizado de cada estudiante.
- Consultar rápidamente los antecedentes de atención.
- Dar continuidad a un caso.
- Controlar seguimientos pendientes.
- Coordinar derivaciones entre profesionales o áreas.
- Identificar casos críticos.
- Mantener información histórica ordenada.
- Obtener reportes consolidados.
- Conocer qué acciones fueron realizadas y por quién.
- Tomar decisiones basadas en información actualizada.

El proyecto propone resolver este problema mediante una plataforma web centralizada y organizada.

---

# 3. Objetivos

## 3.1 Objetivo general

Desarrollar un sistema web que permita centralizar, registrar y gestionar el monitoreo de pacientes universitarios, facilitando el seguimiento de cada caso y mejorando la coordinación entre las diferentes áreas responsables de la atención y acompañamiento del estudiante.

## 3.2 Objetivos específicos

1. Registrar información básica y relevante de los estudiantes atendidos.
2. Facilitar la búsqueda de pacientes mediante información institucional.
3. Registrar las atenciones realizadas por las diferentes áreas.
4. Registrar diagnósticos, observaciones y acciones relacionadas con cada atención.
5. Gestionar el seguimiento de los casos.
6. Registrar acuerdos y compromisos relacionados con el estudiante.
7. Gestionar derivaciones hacia otras áreas responsables.
8. Identificar casos que requieran atención prioritaria.
9. Generar alertas para casos críticos o pendientes.
10. Registrar hospitalizaciones o situaciones que requieran seguimiento especial.
11. Mantener un historial organizado por estudiante.
12. Registrar el cierre o alta de los casos cuando corresponda.
13. Generar reportes y estadísticas para apoyar la toma de decisiones.
14. Controlar el acceso mediante usuarios, roles y permisos.
15. Mantener trazabilidad de las acciones realizadas dentro del sistema.

---

# 4. Público objetivo

## 4.1 Usuarios finales

Los principales usuarios del sistema serán:

- Personal de Bienestar Universitario.
- Médicos.
- Personal de enfermería.
- Psicólogos.
- Docentes autorizados.
- Tutores.
- Pastores.
- Otros profesionales o responsables institucionales autorizados.

## 4.2 Necesidades de los usuarios

Los usuarios requieren:

- Acceso rápido a la información del estudiante.
- Búsqueda sencilla por código u otros datos permitidos.
- Registro rápido de nuevas atenciones.
- Consulta del historial del paciente.
- Visualización del estado actual del caso.
- Registro de seguimientos.
- Gestión de derivaciones.
- Identificación de casos prioritarios.
- Visualización de alertas.
- Control de pendientes.
- Acceso únicamente a la información permitida según su rol.
- Una interfaz clara y fácil de utilizar.

---

# 5. Alcance del proyecto

## 5.1 Dentro del alcance

La primera versión del sistema contempla:

- Inicio y cierre de sesión.
- Administración de usuarios.
- Gestión de roles y permisos.
- Registro de estudiantes/pacientes.
- Edición y consulta de información.
- Búsqueda de pacientes.
- Registro de atenciones.
- Registro de diagnósticos.
- Registro de observaciones.
- Registro de seguimientos.
- Registro de acuerdos y acciones.
- Gestión de derivaciones.
- Clasificación según nivel de prioridad.
- Generación y visualización de alertas.
- Registro de hospitalización cuando corresponda.
- Registro de cierre o alta de casos.
- Consulta del historial del estudiante.
- Generación de reportes básicos.
- Visualización de estadísticas.
- Registro de acciones para auditoría.
- Control de acceso según rol.

## 5.2 Fuera del alcance de la primera versión

No se contempla inicialmente:

- Aplicación móvil nativa para Android o iOS.
- Integración directa con sistemas externos de hospitales.
- Videollamadas o telemedicina.
- Diagnósticos médicos automáticos mediante inteligencia artificial.
- Integración con sensores o dispositivos médicos.
- Sistema de pagos.
- Comunicación automática con entidades externas no autorizadas.
- Funcionalidades avanzadas de inteligencia artificial no aprobadas previamente.

Estas características podrán evaluarse en versiones futuras.

---

# 6. Módulos principales del sistema

El sistema se organizará en **8 módulos funcionales principales**.

---

## Módulo 1. Autenticación y Gestión de Usuarios

### Objetivo

Garantizar que únicamente los usuarios autorizados puedan ingresar al sistema y acceder a las funcionalidades permitidas según su responsabilidad institucional.

### Funciones principales

- Inicio de sesión.
- Cierre de sesión.
- Registro administrativo de usuarios.
- Activación o desactivación de usuarios.
- Gestión de roles.
- Gestión de permisos.
- Restricción de funcionalidades según rol.
- Control del acceso a información sensible.

### Roles considerados

Entre los roles institucionales que podrán configurarse se encuentran:

- Bienestar Universitario.
- Médico.
- Enfermería.
- Psicólogo.
- Docente.
- Tutor.
- Pastor.
- Administrador.

### Resultado esperado

Cada usuario visualizará únicamente las opciones y datos que correspondan a los permisos asignados.

---

## Módulo 2. Gestión de Pacientes / Estudiantes

### Objetivo

Centralizar la información básica, académica y de contacto necesaria para identificar correctamente a cada estudiante atendido.

### Funciones principales

- Registrar estudiantes.
- Editar información permitida.
- Consultar información.
- Buscar estudiantes.
- Buscar por código de estudiante.
- Consultar datos académicos.
- Consultar datos de contacto.
- Registrar contacto de emergencia.
- Acceder al historial general desde la ficha del estudiante.

### Información principal

La ficha puede contener información como:

- Código de estudiante.
- Nombres.
- Apellidos.
- Escuela profesional.
- Teléfono.
- Correo.
- Contacto de emergencia.

### Regla principal

El estudiante debe ser identificado de manera única dentro del sistema.

---

## Módulo 3. Gestión de Casos y Monitoreo

### Objetivo

Permitir controlar el ciclo de vida de los casos que requieren observación, atención o acompañamiento institucional.

### Funciones principales

- Apertura de un caso.
- Consulta del estado del caso.
- Registro de motivo.
- Registro de observaciones.
- Asociación del caso con el estudiante.
- Clasificación del caso.
- Identificación del responsable.
- Registro de acciones realizadas.
- Control de pendientes.
- Actualización del estado.
- Cierre del caso.

### Estados conceptuales posibles

Los estados deberán definirse formalmente durante el modelado de dominio. De manera general, el sistema debe permitir diferenciar casos:

- Activos.
- En seguimiento.
- Pendientes.
- Cerrados.

### Resultado esperado

Bienestar Universitario podrá conocer qué casos continúan activos, cuáles requieren atención y cuáles ya fueron cerrados.

---

## Módulo 4. Gestión de Atenciones y Seguimientos

### Objetivo

Registrar las intervenciones realizadas por los profesionales y conservar la continuidad de la atención.

### Funciones principales

- Registrar una atención.
- Registrar fecha de atención.
- Registrar observaciones.
- Registrar diagnóstico cuando corresponda.
- Identificar al profesional o usuario responsable.
- Asociar la atención con un estudiante.
- Registrar seguimientos posteriores.
- Registrar acuerdos.
- Registrar acciones realizadas.
- Consultar seguimientos anteriores.
- Identificar seguimientos pendientes.

### Áreas que pueden intervenir

- Medicina.
- Enfermería.
- Psicología.
- Tutoría.
- Docencia autorizada.
- Pastoral.
- Bienestar Universitario.
- Otras áreas institucionales autorizadas.

### Resultado esperado

Cada intervención quedará vinculada con el estudiante y podrá consultarse posteriormente como parte de su historial.

---

## Módulo 5. Derivaciones y Coordinación Interdisciplinaria

### Objetivo

Gestionar formalmente el envío de un estudiante desde un área responsable hacia otra cuando el caso requiera atención especializada o complementaria.

### Funciones principales

- Crear una derivación.
- Seleccionar área de destino.
- Registrar motivo.
- Registrar fecha.
- Asociar la derivación con una atención o caso.
- Identificar responsable.
- Consultar derivaciones realizadas.
- Controlar derivaciones pendientes.
- Registrar acciones posteriores relacionadas con la derivación.

### Ejemplos de áreas de destino

- Psicología.
- Nutrición.
- Tutoría.
- Pastoral.
- Medicina.
- Enfermería.
- Bienestar Universitario.

### Resultado esperado

Las áreas involucradas podrán mantener continuidad en el acompañamiento sin perder información relevante del proceso.

---

## Módulo 6. Prioridad, Alertas, Hospitalización y Situaciones Críticas

### Objetivo

Identificar y controlar situaciones que requieran atención rápida o un seguimiento especial.

### Funciones principales

- Clasificar casos según prioridad.
- Identificar casos críticos.
- Generar alertas.
- Mostrar alertas activas.
- Controlar alertas pendientes.
- Registrar hospitalizaciones.
- Registrar establecimiento de salud cuando corresponda.
- Registrar fecha de ingreso.
- Registrar fecha de salida.
- Mantener seguimiento durante una hospitalización.
- Registrar situaciones que requieran atención inmediata.

### Niveles de prioridad

El sistema deberá permitir clasificar casos según los criterios definidos por Bienestar Universitario.

Como referencia funcional, podrán diferenciarse niveles como:

- Prioridad alta.
- Prioridad media.
- Prioridad normal.

La nomenclatura definitiva deberá quedar establecida en las reglas de negocio.

### Resultado esperado

Los usuarios responsables podrán reconocer rápidamente qué estudiantes necesitan atención prioritaria.

---

## Módulo 7. Historial, Cierre y Trazabilidad del Paciente

### Objetivo

Consolidar cronológicamente la información relacionada con cada estudiante y permitir conocer la evolución completa del caso.

### Funciones principales

- Consultar historial del estudiante.
- Visualizar atenciones.
- Visualizar seguimientos.
- Visualizar derivaciones.
- Visualizar hospitalizaciones.
- Visualizar acuerdos.
- Visualizar alertas relacionadas.
- Consultar acciones realizadas.
- Registrar cierre o alta del caso.
- Consultar fecha de cierre.
- Mantener trazabilidad cronológica.

### Resultado esperado

Un usuario autorizado podrá revisar el desarrollo completo del caso sin tener que consultar diferentes registros físicos o fuentes separadas.

---

## Módulo 8. Reportes, Estadísticas y Auditoría

### Objetivo

Transformar la información registrada en datos útiles para la gestión institucional y mantener evidencia de las acciones realizadas dentro del sistema.

### Funciones principales

#### Reportes

- Reportes por período.
- Reportes por estudiante.
- Reportes por escuela profesional.
- Reportes de atenciones.
- Reportes de seguimientos.
- Reportes de derivaciones.
- Reportes de casos activos.
- Reportes de casos cerrados.
- Reportes de hospitalizaciones.

#### Estadísticas

- Cantidad de estudiantes atendidos.
- Número de atenciones.
- Número de seguimientos.
- Cantidad de derivaciones.
- Casos por nivel de prioridad.
- Casos por escuela profesional.
- Casos activos y cerrados.
- Hospitalizaciones registradas.

#### Auditoría

- Registrar acciones importantes.
- Identificar qué usuario realizó una acción.
- Registrar fecha y hora.
- Facilitar trazabilidad.
- Apoyar el control institucional.

### Exportación

Los formatos de exportación podrán definirse en el diseño técnico. La arquitectura debe permitir incorporar formatos como PDF, Excel o CSV sin afectar la lógica principal.

---

# 7. Resumen de los 8 módulos

| N.º | Módulo | Responsabilidad principal |
|---:|---|---|
| 1 | Autenticación y Gestión de Usuarios | Acceso, roles y permisos |
| 2 | Gestión de Pacientes / Estudiantes | Información e identificación del estudiante |
| 3 | Gestión de Casos y Monitoreo | Ciclo de vida y estado de los casos |
| 4 | Gestión de Atenciones y Seguimientos | Intervenciones, diagnósticos, observaciones y seguimiento |
| 5 | Derivaciones y Coordinación Interdisciplinaria | Transferencia y coordinación entre áreas |
| 6 | Prioridad, Alertas, Hospitalización y Situaciones Críticas | Control de casos prioritarios y situaciones especiales |
| 7 | Historial, Cierre y Trazabilidad del Paciente | Consolidación cronológica y cierre |
| 8 | Reportes, Estadísticas y Auditoría | Información gerencial y trazabilidad de acciones |

---

# 8. Flujo general del sistema

```text
Usuario autorizado
        |
        v
Autenticación
        |
        v
Paciente / Estudiante
        |
        v
Caso
        |
        +--------------------+
        |                    |
        v                    v
     Atención           Seguimiento
        |                    |
        +----------+---------+
                   |
                   v
              Derivación
                   |
                   v
          Prioridad / Alertas
                   |
                   v
             Historial
                   |
                   v
       Cierre / Reportes / Auditoría
```

---

# 9. Requisitos funcionales

## RF-01. Autenticación

El sistema debe permitir que usuarios autorizados inicien y cierren sesión.

## RF-02. Roles y permisos

El sistema debe restringir las funcionalidades y la información según el rol del usuario.

## RF-03. Registro de pacientes

El sistema debe permitir registrar estudiantes/pacientes.

## RF-04. Edición de pacientes

El sistema debe permitir modificar información autorizada del estudiante.

## RF-05. Consulta de pacientes

El sistema debe permitir consultar estudiantes registrados.

## RF-06. Búsqueda

El sistema debe permitir localizar estudiantes utilizando datos identificadores permitidos.

## RF-07. Registro de atenciones

El sistema debe permitir registrar las atenciones realizadas.

## RF-08. Diagnósticos y observaciones

El sistema debe permitir registrar diagnósticos y observaciones cuando corresponda.

## RF-09. Seguimientos

El sistema debe permitir registrar y consultar seguimientos.

## RF-10. Acuerdos y acciones

El sistema debe permitir registrar acuerdos y acciones relacionadas con el caso.

## RF-11. Derivaciones

El sistema debe permitir generar derivaciones hacia otras áreas.

## RF-12. Prioridad

El sistema debe permitir clasificar los casos según nivel de prioridad.

## RF-13. Alertas

El sistema debe permitir generar y visualizar alertas.

## RF-14. Hospitalización

El sistema debe permitir registrar información de hospitalización cuando corresponda.

## RF-15. Cierre de caso

El sistema debe permitir registrar el alta o cierre de un caso.

## RF-16. Historial

El sistema debe permitir consultar el historial completo del estudiante.

## RF-17. Reportes

El sistema debe permitir generar reportes de la información registrada.

## RF-18. Estadísticas

El sistema debe permitir visualizar estadísticas generales.

## RF-19. Gestión de usuarios

El sistema debe permitir administrar usuarios y roles de acuerdo con los permisos administrativos.

## RF-20. Auditoría

El sistema debe registrar acciones relevantes realizadas por usuarios autorizados.

---

# 10. Requisitos no funcionales

## RNF-01. Seguridad

El sistema debe proteger la información mediante mecanismos de autenticación y autorización.

## RNF-02. Control de acceso

El acceso debe restringirse según rol y permisos.

## RNF-03. Confidencialidad

El sistema debe proteger los datos personales y la información relacionada con las atenciones.

## RNF-04. Integridad

La información almacenada debe mantener consistencia e integridad.

## RNF-05. Usabilidad

La interfaz debe ser clara, sencilla y comprensible para usuarios con distintos niveles de experiencia tecnológica.

## RNF-06. Compatibilidad

La solución deberá ser compatible con navegadores web modernos.

## RNF-07. Diseño responsive

La interfaz deberá adaptarse a diferentes tamaños de pantalla.

## RNF-08. Rendimiento

Las operaciones principales deberán mantener tiempos de respuesta adecuados.

## RNF-09. Mantenibilidad

El sistema debe permitir correcciones y ampliaciones sin afectar innecesariamente otros componentes.

## RNF-10. Modularidad

La solución debe aplicar alta cohesión y bajo acoplamiento.

## RNF-11. Principios SOLID

El diseño deberá considerar los principios SOLID cuando correspondan.

## RNF-12. Trazabilidad

Las acciones relevantes deberán ser rastreables.

---

# 11. Arquitectura propuesta

## 11.1 Estilo

**Monolito modular con arquitectura en capas.**

El sistema se desarrollará como una única aplicación desplegable, pero internamente estará dividido en módulos funcionales con responsabilidades claras.

## 11.2 Capas principales

```text
Presentación / API
        |
        v
Aplicación / Servicios
        |
        v
Dominio
        |
        v
Persistencia
        |
        v
Base de datos
```

## 11.3 Principios

- Alta cohesión.
- Bajo acoplamiento.
- Separación de responsabilidades.
- Encapsulamiento.
- Modularidad.
- SOLID.
- Mantenibilidad.
- Evolución incremental.

---

# 12. Tecnologías preferidas

## Frontend

```text
HTML
CSS
JavaScript
```

También podrá evaluarse un framework web si posteriormente es aprobado por el equipo.

## Backend

```text
Java
Spring Boot
```

## Base de datos

```text
PostgreSQL
```

## Arquitectura

```text
Monolito modular
Arquitectura en capas
```

## Control de versiones

```text
Git
GitHub
```

Las tecnologías podrán ajustarse durante el diseño técnico siempre que exista una justificación y aprobación correspondiente.

---

# 13. Modelo de información inicial

El modelo inicial contempla como mínimo las siguientes entidades conceptuales:

```text
Paciente
Usuario
Atención
Seguimiento
Derivación
Hospitalización
```

Relaciones conceptuales principales:

```text
Paciente
   |
   +---- Atención
            |
            +---- Seguimiento
            |
            +---- Derivación
            |
            +---- Hospitalización
```

La ampliación del modelo deberá realizarse conforme se definan formalmente casos, alertas, acuerdos, auditoría y demás componentes del dominio.

---

# 14. Datos principales del paciente

Entre los datos identificados para la gestión del estudiante se consideran:

- Código de estudiante.
- Nombres.
- Apellidos.
- Escuela profesional.
- Teléfono.
- Correo.
- Contacto de emergencia.

La información definitiva deberá respetar los requerimientos levantados y las restricciones de privacidad establecidas por la institución.

---

# 15. Reglas de negocio generales

## RN-01

Cada estudiante debe contar con un identificador único dentro del sistema.

## RN-02

Una atención debe estar asociada con un estudiante existente.

## RN-03

Un seguimiento debe estar relacionado con una atención o caso válido.

## RN-04

Una derivación debe indicar el área responsable de destino.

## RN-05

Las acciones relacionadas con información sensible solo podrán ser realizadas por usuarios autorizados.

## RN-06

La clasificación de prioridad deberá seguir los criterios definidos por Bienestar Universitario.

## RN-07

Los casos críticos o pendientes deberán poder identificarse mediante alertas.

## RN-08

El cierre de un caso debe conservar la información histórica.

## RN-09

La información histórica no debe perderse al finalizar un caso.

## RN-10

Las acciones relevantes deberán mantener trazabilidad del usuario responsable.

## RN-11

Los reportes solo podrán mostrar información a la cual el usuario tenga autorización.

## RN-12

La información del estudiante deberá manejarse con confidencialidad.

---

# 16. Actores del sistema

| Actor | Responsabilidad general |
|---|---|
| Administrador | Usuarios, roles, permisos y configuración autorizada |
| Bienestar Universitario | Supervisión y gestión general de casos |
| Médico | Registro y consulta de atenciones correspondientes |
| Enfermería | Registro y seguimiento de atenciones correspondientes |
| Psicólogo | Gestión de atenciones y seguimientos psicológicos autorizados |
| Docente | Participación dentro de las funciones que se le autoricen |
| Tutor | Seguimiento y acompañamiento institucional |
| Pastor | Acompañamiento pastoral autorizado |

---

# 17. Casos de uso principales

1. Iniciar sesión.
2. Buscar estudiante.
3. Registrar estudiante.
4. Consultar ficha del estudiante.
5. Registrar atención.
6. Registrar diagnóstico u observación.
7. Registrar seguimiento.
8. Registrar acuerdo.
9. Crear derivación.
10. Clasificar prioridad.
11. Generar alerta.
12. Registrar hospitalización.
13. Consultar historial.
14. Cerrar caso.
15. Consultar casos pendientes.
16. Generar reporte.
17. Consultar estadísticas.
18. Gestionar usuarios.
19. Gestionar roles.
20. Consultar auditoría según autorización.

---

# 18. Criterios de aceptación generales

Una funcionalidad se considerará aceptada cuando:

- Cumpla el requerimiento definido.
- Respete los permisos del usuario.
- Registre correctamente la información.
- Mantenga integridad de los datos.
- Muestre mensajes comprensibles.
- No exponga información no autorizada.
- Mantenga trazabilidad cuando corresponda.
- Permita consultar posteriormente la información registrada.
- Sea compatible con la arquitectura definida.

---

# 19. Entregables

Los principales entregables del proyecto contemplan:

- Project Brief.
- Documento de requisitos.
- Requisitos funcionales.
- Requisitos no funcionales.
- Reglas de negocio.
- Diagramas C4.
- Diagramas UML según avance académico.
- Modelo de datos.
- Diccionario de datos.
- Diseño de arquitectura.
- Código fuente backend.
- Código fuente frontend.
- Scripts de base de datos.
- Documentación de API.
- Casos y evidencias de prueba.
- Manual técnico.
- Manual básico de usuario.
- Documentación de despliegue cuando corresponda.

---

# 20. Cronograma general

El proyecto será desarrollado durante el semestre académico.

## Fase 1 — Análisis

- Levantamiento de información.
- Identificación del problema.
- Project Brief.
- Identificación de actores.
- Requisitos.
- Reglas de negocio.

## Fase 2 — Diseño

- Arquitectura.
- Modelo C4.
- Diseño modular.
- Modelo de dominio.
- Diagramas UML.
- Modelo de datos.

## Fase 3 — Desarrollo

- Backend.
- Base de datos.
- Frontend.
- Integración de módulos.
- Seguridad.

## Fase 4 — Pruebas

- Pruebas funcionales.
- Validaciones.
- Integración.
- Corrección de errores.

## Fase 5 — Entrega

- Documentación final.
- Evidencias.
- Demostración funcional.
- Sustentación técnica.

---

# 21. Riesgos del proyecto

| Riesgo | Impacto | Mitigación |
|---|---|---|
| Exposición de información sensible | Alto | Autenticación, roles, permisos y control de acceso |
| Requisitos incompletos | Alto | Validación continua con responsables |
| Pérdida de trazabilidad | Alto | Registro de acciones y auditoría |
| Duplicación de estudiantes | Medio/Alto | Identificador institucional único |
| Casos sin seguimiento | Alto | Alertas y control de pendientes |
| Acoplamiento excesivo | Medio/Alto | Arquitectura modular y SOLID |
| Errores de integridad | Alto | Validaciones y restricciones de base de datos |
| Retrasos académicos | Medio | Desarrollo incremental por módulos |
| Incorporación de funciones no aprobadas | Medio | Control de alcance y validación previa |

---

# 22. Restricciones

- El proyecto se desarrollará dentro del período académico.
- El equipo estará conformado principalmente por estudiantes.
- Se utilizarán los recursos tecnológicos disponibles.
- El acceso a información sensible estará restringido.
- Se deberá respetar la confidencialidad de los datos.
- Las funcionalidades deben mantenerse alineadas con los requerimientos levantados.
- No deberán incorporarse tecnologías o funciones no validadas.
- La primera versión será web.
- No será una aplicación móvil nativa.
- No realizará diagnósticos médicos mediante IA.
- No incluirá telemedicina.
- No incluirá pagos.
- No se integrará automáticamente con entidades externas no autorizadas.

---

# 23. Métricas de éxito

El proyecto podrá evaluarse mediante indicadores como:

- Porcentaje de módulos funcionales implementados.
- Porcentaje de requisitos funcionales completados.
- Cantidad de casos registrados correctamente.
- Cantidad de seguimientos trazables.
- Cantidad de derivaciones controladas.
- Capacidad de identificar casos pendientes.
- Correcto funcionamiento de roles y permisos.
- Integridad de información almacenada.
- Correcta generación de reportes.
- Cumplimiento de pruebas funcionales.
- Cumplimiento del cronograma académico.

---

# 24. Trazabilidad académica

El proyecto puede utilizarse como caso integrador entre diferentes cursos de Ingeniería de Sistemas.

## Análisis y Diseño de Sistemas

- Arquitectura.
- C4.
- SOLID.
- UML.
- Diseño del dominio.
- Patrones.

## Lenguaje de Programación II

- Backend.
- Servicios REST.
- Modularidad.
- Validaciones.
- Integración Full-Stack.

## Base de Datos II

- Modelo físico.
- Integridad.
- Consultas.
- Procedimientos y funciones según avance.
- Seguridad.
- Optimización.
- Auditoría.

---

# 25. Visión de evolución

La primera versión busca resolver la necesidad principal de centralización y seguimiento.

En versiones futuras, y únicamente después de su validación, podrán evaluarse:

- Nuevos tipos de reportes.
- Integraciones institucionales.
- Canales autorizados de notificación.
- Mejoras de analítica.
- Aplicación móvil.
- Nuevas áreas de atención.
- Funcionalidades adicionales de apoyo a Bienestar Universitario.

---

# 26. Principio rector del proyecto

> **Toda la información relevante del seguimiento del estudiante debe estar organizada, protegida, disponible para los usuarios autorizados y ser trazable durante todo el ciclo de atención.**

---

## Resumen ejecutivo de módulos

```text
1. Autenticación y Gestión de Usuarios
2. Gestión de Pacientes / Estudiantes
3. Gestión de Casos y Monitoreo
4. Gestión de Atenciones y Seguimientos
5. Derivaciones y Coordinación Interdisciplinaria
6. Prioridad, Alertas, Hospitalización y Situaciones Críticas
7. Historial, Cierre y Trazabilidad del Paciente
8. Reportes, Estadísticas y Auditoría
```

---

## Estado del documento

Este Project Brief constituye la base funcional y técnica de alto nivel del **Sistema Web de Monitoreo de Pacientes Universitarios**.

Los requisitos detallados, reglas de negocio, modelo de dominio, casos de uso, diagramas C4, UML, modelo relacional y contratos de API deberán mantenerse alineados con este documento y actualizarse únicamente cuando exista una decisión validada del proyecto.
