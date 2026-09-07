# BomERP — Project Brief

> **Proyecto académico de Lenguaje de Programación II (LP2)**  
> **Universidad Peruana Unión (UPEU)**  
> **Tipo de solución:** Backend REST empresarial modular  
> **Arquitectura:** Monolito modular con Spring Modulith  
> **Estado documentado:** avance hasta S04 — módulo de Ventas  
> **Fecha de actualización:** 07 de septiembre de 2026

---

## 1. Información general

| Campo | Detalle |
|---|---|
| **Nombre del proyecto** | BomERP |
| **Curso principal** | Lenguaje de Programación II (LP2) |
| **Institución** | Universidad Peruana Unión — UPEU |
| **Tipo de aplicación** | Backend REST empresarial |
| **Lenguaje principal** | Java 21 |
| **Framework** | Spring Boot 4.0.7 |
| **Arquitectura** | Monolito modular |
| **Gestión de módulos** | Spring Modulith |
| **Persistencia** | Spring Data JPA + Oracle Database |
| **Gestor de dependencias** | Maven |
| **Formato de despliegue** | Un solo artefacto `.jar` |
| **Repositorio de trabajo** | `LP2clases` |
| **Estado actual** | Catálogo implementado y módulo de Ventas en desarrollo/integración |

---

## 2. Resumen ejecutivo

**BomERP** es una base backend Full-Stack modular desarrollada como proyecto académico para el curso de **Lenguaje de Programación II**. Su propósito es construir progresivamente un sistema empresarial basado en servicios REST, aplicando buenas prácticas de arquitectura de software, persistencia, validaciones, reglas de negocio, transacciones, documentación de API, pruebas y separación entre módulos.

El proyecto inicia con el módulo de **Catálogo**, compuesto por **Categorías** y **Productos**, y posteriormente incorpora el módulo de **Ventas**, utilizando una estructura de cabecera-detalle. La solución está diseñada como un **monolito modular**, donde cada módulo de negocio mantiene responsabilidades claramente delimitadas y se comunica con otros módulos únicamente mediante contratos públicos.

BomERP sirve además como punto de integración académica entre **LP2**, **Análisis y Diseño de Sistemas (ADS)** y **Base de Datos II (BD2)**.

---

## 3. Problema que aborda

En aplicaciones empresariales es común que el crecimiento desordenado del código produzca:

- Alto acoplamiento entre componentes.
- Acceso directo e indebido entre repositorios.
- Dificultad para mantener y probar funcionalidades.
- Reglas de negocio mezcladas con controladores.
- Falta de contratos claros entre módulos.
- Duplicación de lógica.
- Errores de integridad de datos.
- Dependencia excesiva entre capas.
- Dificultad para evolucionar hacia nuevos módulos.

BomERP busca resolver estos problemas mediante una organización modular y por capas, contratos REST consistentes, separación de responsabilidades y control explícito de las dependencias entre módulos.

---

## 4. Objetivo general

Diseñar e implementar un backend REST empresarial modular utilizando **Java 21, Spring Boot, Spring Modulith y Oracle Database**, aplicando arquitectura por módulos de negocio, separación por capas, buenas prácticas de programación, validaciones, persistencia, transacciones y documentación de servicios.

---

## 5. Objetivos específicos

1. Implementar una API REST versionada bajo `/api/v1`.
2. Organizar el sistema por módulos de negocio y no únicamente por capas globales.
3. Implementar operaciones CRUD para las entidades principales.
4. Gestionar correctamente la relación entre **Categoría** y **Producto**.
5. Implementar operaciones transaccionales para el módulo de **Ventas**.
6. Aplicar reglas de negocio como validación de disponibilidad de stock.
7. Mantener aislados los repositorios de cada módulo.
8. Exponer servicios públicos controlados entre módulos.
9. Documentar la API mediante OpenAPI/Swagger.
10. Aplicar validaciones de entrada mediante Jakarta Validation.
11. Manejar errores HTTP de forma consistente.
12. Verificar los límites de arquitectura mediante Spring Modulith.
13. Conectar el backend con una base de datos Oracle.
14. Integrar conocimientos de LP2, ADS y BD2 en una única solución.
15. Preparar una base sostenible para incorporar nuevos módulos empresariales.

---

## 6. Alcance del proyecto

### 6.1 Incluido en el alcance

El proyecto contempla:

- Backend REST.
- Arquitectura modular.
- Persistencia con Oracle.
- Gestión de categorías.
- Gestión de productos.
- Relación Categoría–Producto.
- Gestión de ventas.
- Detalle de ventas.
- Validación de stock.
- Transacciones.
- DTO de entrada y salida.
- Validaciones.
- Manejo de errores.
- Consultas y reportes.
- CORS.
- Logs.
- Spring Boot Actuator.
- OpenAPI/Swagger.
- Pruebas de modularidad.
- Integración con objetos desarrollados en BD2.
- Evolución progresiva por sesiones académicas.

### 6.2 Fuera del alcance actual

En la etapa actual no se considera como funcionalidad terminada:

- Frontend completo.
- Aplicación móvil.
- Microservicios distribuidos.
- Autenticación y autorización completa.
- OAuth2.
- JWT como requisito actual.
- Despliegue productivo en nube.
- Módulo de compras terminado.
- Seguridad empresarial completa.

Estas funcionalidades pueden incorporarse en fases posteriores.

---

## 7. Público objetivo

### Usuarios técnicos

- Estudiantes de Ingeniería de Sistemas.
- Docente del curso LP2.
- Equipo de desarrollo del proyecto.
- Integrantes responsables de ADS.
- Integrantes responsables de BD2.

### Usuarios funcionales futuros

Al evolucionar como ERP, la solución podría ser utilizada por:

- Administradores.
- Personal de ventas.
- Responsables de inventario.
- Personal encargado de catálogo.
- Usuarios autorizados mediante el futuro módulo de seguridad.

---

## 8. Arquitectura de software

### 8.1 Estilo arquitectónico

BomERP utiliza un:

> **Monolito modular con Spring Modulith**

La aplicación:

- Tiene un solo proyecto Maven.
- Genera un solo archivo `.jar`.
- Se ejecuta como una sola aplicación Spring Boot.
- Divide internamente sus responsabilidades por módulos de negocio.
- Evita dependencias indiscriminadas entre módulos.
- Puede evolucionar de manera ordenada sin adoptar microservicios prematuramente.

---

## 9. Regla principal de modularidad

La regla arquitectónica fundamental es:

> **Un módulo NO debe acceder directamente al repositorio de otro módulo.**

La comunicación entre módulos debe realizarse mediante:

- Servicios públicos.
- DTO públicos.
- Interfaces explícitamente expuestas.
- `@NamedInterface` cuando corresponda.

### Ejemplo

El módulo `ventas` necesita consultar información de productos.

**Incorrecto:**

```text
ventas -> ProductoRepository
```

**Correcto:**

```text
ventas -> ProductoService público -> ProductoRepository
```

De esta forma se mantiene el encapsulamiento del módulo `catalogo`.

---

## 10. Organización por módulos

La arquitectura sigue el principio:

> **Primero módulo de negocio, luego capas internas.**

Estructura conceptual:

```text
pe.edu.upeu.bomerp
│
├── catalogo
│   ├── categoria
│   │   ├── controller
│   │   ├── dto
│   │   ├── entity
│   │   ├── repository
│   │   └── service
│   │
│   └── producto
│       ├── controller
│       ├── dto
│       ├── entity
│       ├── repository
│       └── service
│
├── ventas
│   └── venta
│       ├── controller
│       ├── dto
│       ├── entity
│       ├── repository
│       └── service
│
└── BomerpBackendApplication.java
```

No deben crearse paquetes vacíos únicamente para anticipar futuras funcionalidades.

---

## 11. Estructura general del proyecto

```text
lp2/
└── bomerp-backend/
    ├── pom.xml
    ├── compose-dev.yml
    │
    ├── src/
    │   ├── main/
    │   │   ├── java/
    │   │   │   └── pe/
    │   │   │       └── edu/
    │   │   │           └── upeu/
    │   │   │               └── bomerp/
    │   │   │                   ├── BomerpBackendApplication.java
    │   │   │                   ├── config/
    │   │   │                   │   └── OpenApiConfig.java
    │   │   │                   ├── catalogo/
    │   │   │                   └── ventas/
    │   │   │
    │   │   └── resources/
    │   │       ├── application.yml
    │   │       └── application-dev.yml
    │   │
    │   └── test/
    │       └── java/
    │           └── ModularityTests.java
    │
    └── target/
```

> `target/` no debe versionarse en Git.

---

# 12. Módulos funcionales

## 12.1 Módulo Catálogo

Responsable de administrar la información base de productos.

Submódulos:

- Categoría.
- Producto.

### Responsabilidades

- Registrar categorías.
- Consultar categorías.
- Actualizar categorías.
- Eliminar categorías según reglas permitidas.
- Registrar productos.
- Consultar productos.
- Actualizar productos.
- Eliminar productos.
- Asociar productos con categorías.
- Proporcionar información de productos a otros módulos mediante servicios públicos.

---

## 12.2 Categoría

Estructura interna:

```text
categoria/
├── controller/
├── dto/
├── entity/
├── repository/
└── service/
```

### Capas

**Controller**
- Recibe peticiones HTTP.
- Valida parámetros básicos.
- Invoca la capa de servicio.
- Devuelve respuestas HTTP.

**DTO**
- Define los datos expuestos por la API.
- Evita exponer directamente las entidades JPA.

**Entity**
- Representa el modelo persistente.

**Repository**
- Gestiona acceso a datos mediante Spring Data JPA.

**Service**
- Contiene reglas y lógica de negocio.

---

## 12.3 Producto

Estructura interna:

```text
producto/
├── controller/
├── dto/
├── entity/
├── repository/
└── service/
```

### Relación principal

```text
Categoria 1 ---- N Producto
```

Una categoría puede contener múltiples productos y un producto pertenece a una categoría según el modelo definido para el proyecto.

---

# 13. Módulo Ventas

El módulo de Ventas incorpora una operación empresarial de mayor complejidad utilizando el patrón:

> **Cabecera — Detalle**

Entidades principales:

- `Venta`
- `DetalleVenta`
- `EstadoVenta`

Tablas principales en Oracle:

- `VENTAS`
- `DETALLE_VENTAS`

Esquema de base de datos utilizado para este módulo:

```text
BOM_VENTAS
```

El usuario de aplicación debe contar únicamente con los permisos necesarios sobre los objetos que requiere.

---

## 14. Modelo conceptual de ventas

```text
VENTA
│
├── datos generales
├── estado
└── detalles
     │
     ├── producto 1
     ├── cantidad
     ├── precio
     │
     ├── producto 2
     ├── cantidad
     └── precio
```

Relación:

```text
Venta 1 ---- N DetalleVenta
```

---

## 15. Regla de negocio de stock

Al registrar una venta:

1. Se recibe la cabecera de la venta.
2. Se reciben uno o más detalles.
3. Se consulta cada producto mediante el contrato público del módulo Catálogo.
4. Se verifica la existencia del producto.
5. Se valida el stock disponible.
6. Se procesan los detalles.
7. Se persiste la operación.
8. La operación debe conservar consistencia transaccional.

Si el stock es insuficiente, la API debe responder:

```http
409 Conflict
```

La venta no debe quedar registrada parcialmente.

---

## 16. Transacciones

Las operaciones de ventas que modifican varias entidades deben ejecutarse de manera transaccional.

Principio esperado:

```text
TODO SE CONFIRMA
o
NADA SE CONFIRMA
```

Una falla durante el procesamiento debe provocar rollback de la operación cuando corresponda.

---

# 17. Contratos públicos entre módulos

El módulo de Catálogo puede exponer servicios y DTO necesarios para otros módulos.

Ejemplo conceptual:

```text
catalogo.producto.service
catalogo.producto.dto
```

Estos paquetes pueden declararse como interfaces públicas mediante Spring Modulith.

El objetivo es permitir:

```text
Ventas -> Servicio público de Producto
```

y evitar:

```text
Ventas -> Repository de Producto
```

---

# 18. API REST

## 18.1 Convención base

Las rutas del proyecto utilizan versionado:

```text
/api/v1
```

---

## 18.2 Categorías

Ruta base:

```http
/api/v1/categorias
```

Operaciones consideradas en la evolución del proyecto:

| Método | Endpoint | Descripción |
|---|---|---|
| `GET` | `/api/v1/categorias` | Listar categorías |
| `GET` | `/api/v1/categorias/{id}` | Obtener categoría |
| `POST` | `/api/v1/categorias` | Registrar categoría |
| `PUT` | `/api/v1/categorias/{id}` | Actualizar categoría |
| `DELETE` | `/api/v1/categorias/{id}` | Eliminar categoría |

---

## 18.3 Productos

Ruta base:

```http
/api/v1/productos
```

| Método | Endpoint | Descripción |
|---|---|---|
| `GET` | `/api/v1/productos` | Listar productos |
| `GET` | `/api/v1/productos/{id}` | Obtener producto |
| `POST` | `/api/v1/productos` | Registrar producto |
| `PUT` | `/api/v1/productos/{id}` | Actualizar producto |
| `DELETE` | `/api/v1/productos/{id}` | Eliminar producto |

---

## 18.4 Ventas

Ruta prevista/implementada durante S04:

```http
POST /api/v1/ventas
```

Responsabilidades:

- Recibir un DTO compuesto.
- Registrar cabecera.
- Registrar detalles.
- Consultar productos.
- Validar stock.
- Aplicar reglas de negocio.
- Ejecutar la operación de forma transaccional.
- Devolver el resultado correspondiente.

---

# 19. Códigos HTTP

La API debe utilizar códigos HTTP de forma coherente.

| Código | Significado en BomERP |
|---:|---|
| `200 OK` | Consulta o actualización correcta |
| `201 Created` | Recurso creado correctamente |
| `204 No Content` | Eliminación correcta sin cuerpo de respuesta |
| `400 Bad Request` | Datos de entrada inválidos |
| `404 Not Found` | Recurso no encontrado |
| `409 Conflict` | Conflicto con una regla de negocio, por ejemplo stock insuficiente |
| `500 Internal Server Error` | Error interno no controlable desde el cliente |
| `401 Unauthorized` | Reservado para la fase de seguridad |
| `403 Forbidden` | Reservado para la fase de seguridad |

---

# 20. DTO

Los DTO se utilizan para separar:

```text
API <-> Modelo de dominio/persistencia
```

Ventajas:

- Evitan exponer entidades JPA directamente.
- Permiten controlar los campos publicados.
- Facilitan validaciones.
- Reducen acoplamiento.
- Permiten evolucionar la base de datos sin romper necesariamente el contrato REST.

Tipos considerados:

- DTO de entrada.
- DTO de salida.
- DTO compuesto para operaciones de cabecera-detalle.

---

# 21. Validaciones

Las entradas deben validarse con Jakarta Validation cuando corresponda.

Ejemplos de validaciones esperadas:

- Campos obligatorios.
- Longitudes.
- Cantidades mayores a cero.
- Identificadores válidos.
- Formatos correctos.
- Valores permitidos.
- Existencia de relaciones.
- Integridad de operaciones.

El Controller no debe contener reglas empresariales complejas; estas deben residir principalmente en Service.

---

# 22. Manejo de errores

El proyecto debe manejar de manera consistente:

- Validaciones fallidas.
- Recursos inexistentes.
- Conflictos de negocio.
- Errores de persistencia.
- Errores internos.

Categorías principales:

```text
400 - Datos inválidos
404 - No encontrado
409 - Conflicto de negocio
500 - Error interno
```

Los mensajes de error no deben revelar:

- Contraseñas.
- Cadenas de conexión.
- Secretos.
- Stack traces internos al consumidor final.
- Información sensible de infraestructura.

---

# 23. Base de datos

## Motor

```text
Oracle Database Free
```

Contenedor de desarrollo:

```text
gvenzl/oracle-free:23-slim
```

Servicio utilizado:

```text
FREEPDB1
```

---

## 23.1 Estrategia JPA

La aplicación no debe depender de Hibernate para crear automáticamente el esquema productivo.

Configuración esperada:

```properties
spring.jpa.hibernate.ddl-auto=validate
```

Esto permite verificar que las entidades JPA sean compatibles con las estructuras existentes en Oracle.

---

## 23.2 Integración con BD2

BD2 es responsable de aportar y evolucionar los objetos de base de datos requeridos por el proyecto.

Ejemplos:

```text
CATEGORIA
PRODUCTO
VENTAS
DETALLE_VENTAS
```

En fases posteriores pueden incorporarse objetos PL/SQL, por ejemplo procedimientos o paquetes relacionados con el registro de ventas.

---

# 24. Seguridad de credenciales

## Regla obligatoria

Nunca se deben subir al repositorio:

- Contraseñas.
- Tokens.
- Secrets.
- Credenciales Oracle.
- Variables privadas.
- Archivos `.env` con valores reales.
- Llaves privadas.

Se recomienda usar:

```text
Variables de entorno
```

y mantener archivos sensibles fuera del control de versiones.

Ejemplo conceptual:

```properties
DB_URL=${DB_URL}
DB_USERNAME=${DB_USERNAME}
DB_PASSWORD=${DB_PASSWORD}
```

---

# 25. Tecnologías

| Tecnología | Uso |
|---|---|
| **Java 21** | Lenguaje principal |
| **Spring Boot 4.0.7** | Framework backend |
| **Spring Web** | API REST |
| **Spring Data JPA** | Persistencia |
| **Jakarta Validation** | Validaciones |
| **Oracle JDBC Driver** | Conectividad con Oracle |
| **Spring Modulith** | Arquitectura modular |
| **SpringDoc OpenAPI** | Documentación de API |
| **Spring Boot Actuator** | Observabilidad |
| **Maven** | Dependencias y build |
| **Docker** | Infraestructura local |
| **Oracle Database Free** | Base de datos |
| **Lombok** | Reducción de código repetitivo |
| **Spring Boot DevTools** | Desarrollo local |
| **Git** | Control de versiones |
| **GitHub** | Repositorio remoto |
| **VS Code** | Entorno principal de desarrollo |

---

# 26. Dependencias relevantes

El `pom.xml` centraliza las dependencias de toda la aplicación.

Dependencias esperadas:

```text
Spring Web
Spring Data JPA
Validation
Oracle Driver
SpringDoc OpenAPI
Spring Boot Actuator
Spring Modulith
Lombok
Spring Boot DevTools
Testing
```

### Restricción

No debe agregarse:

```text
spring-modulith-starter-jpa
```

si la guía del proyecto establece su eliminación para la configuración actual.

---

# 27. Configuración OpenAPI

Archivo de configuración:

```text
OpenApiConfig.java
```

Objetivo:

- Documentar los endpoints.
- Mostrar contratos REST.
- Facilitar pruebas manuales.
- Mejorar la comunicación entre backend y futuros clientes frontend.

La documentación debe mantenerse sincronizada con el comportamiento real de la API.

---

# 28. Observabilidad

La solución contempla:

### Logs

Los logs deben servir para:

- Identificar errores.
- Seguir operaciones.
- Facilitar depuración.
- Analizar fallos.

No deben registrar secretos.

### Actuator

Spring Boot Actuator puede utilizarse para exponer información técnica controlada sobre:

- Estado de la aplicación.
- Salud.
- Métricas permitidas.

---

# 29. CORS

En las fases donde se integre un frontend, se configurará CORS para permitir únicamente los orígenes requeridos.

No debe utilizarse una política excesivamente abierta en un entorno productivo sin justificación.

---

# 30. Pruebas

## 30.1 Prueba de modularidad

Archivo:

```text
ModularityTests.java
```

Objetivo:

- Verificar la estructura modular.
- Detectar dependencias prohibidas.
- Validar límites entre módulos.
- Evitar ciclos arquitectónicos.

---

## 30.2 Pruebas funcionales

La evolución del proyecto debe contemplar:

- Pruebas de servicios.
- Pruebas de repositorios cuando sean necesarias.
- Pruebas de endpoints.
- Pruebas de validación.
- Pruebas de reglas de negocio.
- Pruebas transaccionales.

---

# 31. Decisiones de arquitectura

El proyecto utiliza ADR (*Architecture Decision Records*) para documentar decisiones relevantes.

Referencias iniciales:

```text
ADR-001
ADR-002
```

Un ADR debe permitir comprender:

- Contexto.
- Problema.
- Decisión.
- Alternativas.
- Consecuencias.

---

# 32. Principios de diseño

BomERP busca cumplir, entre otros, los siguientes principios:

### Separación de responsabilidades

Cada capa tiene una responsabilidad definida.

### Bajo acoplamiento

Los módulos se comunican mediante contratos públicos.

### Alta cohesión

Cada módulo contiene elementos relacionados con su propio dominio.

### Encapsulamiento

Los detalles internos de persistencia no deben ser consumidos directamente desde otros módulos.

### Evolución incremental

Las funcionalidades se incorporan por sesiones sin crear estructuras innecesarias anticipadamente.

---

# 33. Convenciones de código

## Paquetes

Formato base:

```text
pe.edu.upeu.bomerp
```

## Capas internas

```text
controller
dto
entity
repository
service
```

## Nombres

- Clases: `PascalCase`
- Métodos: `camelCase`
- Variables: `camelCase`
- Constantes: `UPPER_SNAKE_CASE`
- Paquetes: minúsculas

---

# 34. Flujo general de una petición

```text
Cliente
  |
  v
Controller
  |
  v
DTO
  |
  v
Service
  |
  v
Repository
  |
  v
Oracle Database
```

Respuesta:

```text
Oracle Database
  |
  v
Repository
  |
  v
Service
  |
  v
DTO Response
  |
  v
Controller
  |
  v
Cliente
```

---

# 35. Flujo entre módulos

Ejemplo de Venta consultando Producto:

```text
VentaController
      |
      v
VentaService
      |
      v
ProductoService
      |
      v
ProductoRepository
      |
      v
Oracle
```

No debe ocurrir:

```text
VentaService
      |
      X
ProductoRepository
```

si el repositorio pertenece al módulo Catálogo.

---

# 36. Entornos de configuración

Configuraciones principales:

```text
application.yml
application-dev.yml
```

Objetivo:

- Separar configuración general.
- Facilitar desarrollo local.
- Evitar valores sensibles dentro del código.
- Permitir evolución hacia otros perfiles.

---

# 37. Docker

Docker se utiliza principalmente para levantar la infraestructura local requerida por el backend.

Archivo actual de referencia:

```text
compose-dev.yml
```

El entorno permite ejecutar Oracle Database de forma reproducible sin instalar toda la infraestructura directamente dentro del proyecto.

---

# 38. Build

El proyecto utiliza Maven.

Compilar:

```bash
mvn clean package
```

Ejecutar pruebas:

```bash
mvn test
```

Ejecutar Spring Boot:

```bash
mvn spring-boot:run
```

El resultado del build se genera en:

```text
target/
```

---

# 39. Git y GitHub

El repositorio debe contener únicamente archivos necesarios para reconstruir el proyecto.

## No versionar

```text
target/
.env
*.log
credenciales
secretos
archivos temporales
configuraciones locales sensibles
```

## Sí versionar

```text
src/
pom.xml
compose-dev.yml
README.md
PROJECT_BRIEF.md
documentación
scripts SQL permitidos
ADR
```

---

# 40. Estrategia de desarrollo

Flujo sugerido:

```text
main
  |
  ├── feature/catalogo
  ├── feature/productos
  ├── feature/ventas
  ├── fix/...
  └── docs/...
```

Cada cambio debe:

1. Resolver una tarea concreta.
2. Mantener compilación.
3. Respetar límites modulares.
4. Evitar subir secretos.
5. Incluir documentación cuando cambie un contrato.
6. Mantener nombres consistentes.

---

# 41. Roadmap académico

## S01 — Base Backend

- Java y entorno.
- Proyecto Spring Boot.
- Oracle.
- REST.
- OpenAPI.
- Primeros endpoints.
- Estructura inicial.

## S02 — CRUD y validaciones

- Operaciones CRUD.
- DTO de entrada.
- DTO de salida.
- Validaciones.
- Manejo de errores.

## S03 — Relaciones y modularidad

- Relación Categoría–Producto.
- Servicios.
- Spring Modulith.
- Límites entre módulos.
- Pruebas de modularidad.
- Trazabilidad LP2–ADS–BD2.

## S04 — Ventas y transacciones

- Módulo `ventas`.
- Entidad `Venta`.
- Entidad `DetalleVenta`.
- `EstadoVenta`.
- Cabecera-detalle.
- DTO compuesto.
- Integración con Producto.
- Interfaces públicas.
- Validación de stock.
- Transacciones.
- Error `409 Conflict` ante stock insuficiente.
- Tablas Oracle `VENTAS` y `DETALLE_VENTAS`.

## S05 — Consultas e integración

- Consultas.
- Reportes.
- CORS.
- Integración con consumidores de la API.
- Logs.

## S06 — Producto de Unidad 1

- Consolidación de funcionalidades.
- Correcciones.
- Validaciones finales.
- Presentación del producto de la unidad.

## Fases posteriores

Pueden incluir:

- Compras.
- Seguridad.
- Autenticación.
- Autorización.
- Nuevos módulos empresariales.

El módulo `seguridad` está previsto para una fase posterior del curso y no debe adelantarse creando paquetes vacíos sin necesidad.

---

# 42. Integración LP2 — ADS — BD2

## LP2

Responsable de:

- Backend.
- Java.
- Spring Boot.
- API REST.
- Servicios.
- Validaciones.
- Transacciones.
- Integración de módulos.

## ADS

Aporta:

- Diseño de componentes.
- Responsabilidades.
- Principios SOLID.
- Arquitectura.
- Diagramas.
- Decisiones de diseño.

## BD2

Aporta:

- Modelo físico.
- Tablas.
- Restricciones.
- Relaciones.
- Usuarios y esquemas Oracle.
- Objetos PL/SQL cuando corresponda.
- Integridad de datos.

### Trazabilidad

```text
ADS
  |
  | diseño
  v
LP2
  |
  | implementación
  v
BD2
```

En la práctica existe retroalimentación entre las tres áreas.

---

# 43. Requisitos funcionales

| ID | Requisito |
|---|---|
| **RF-01** | El sistema debe permitir consultar categorías. |
| **RF-02** | El sistema debe permitir registrar categorías. |
| **RF-03** | El sistema debe permitir actualizar categorías. |
| **RF-04** | El sistema debe permitir eliminar categorías según las reglas definidas. |
| **RF-05** | El sistema debe permitir consultar productos. |
| **RF-06** | El sistema debe permitir registrar productos. |
| **RF-07** | El sistema debe permitir actualizar productos. |
| **RF-08** | El sistema debe permitir eliminar productos según las reglas definidas. |
| **RF-09** | El sistema debe asociar productos con categorías. |
| **RF-10** | El sistema debe permitir registrar una venta. |
| **RF-11** | Una venta debe admitir uno o más detalles. |
| **RF-12** | Cada detalle debe referenciar un producto válido. |
| **RF-13** | El sistema debe validar la disponibilidad de stock. |
| **RF-14** | El sistema debe rechazar una venta cuando el stock sea insuficiente. |
| **RF-15** | El registro de una venta debe ejecutarse de manera transaccional. |
| **RF-16** | El sistema debe devolver códigos HTTP acordes al resultado de la operación. |
| **RF-17** | El sistema debe exponer documentación OpenAPI de sus contratos. |
| **RF-18** | El sistema debe permitir incorporar consultas y reportes en la evolución del proyecto. |

---

# 44. Requisitos no funcionales

| ID | Requisito |
|---|---|
| **RNF-01** | El backend debe utilizar Java 21. |
| **RNF-02** | La aplicación debe usar Spring Boot 4.0.7. |
| **RNF-03** | La solución debe mantener una arquitectura modular. |
| **RNF-04** | Los módulos no deben acceder directamente a repositorios ajenos. |
| **RNF-05** | La persistencia debe utilizar Oracle Database. |
| **RNF-06** | La aplicación debe utilizar Spring Data JPA. |
| **RNF-07** | El esquema debe validarse con `ddl-auto=validate`. |
| **RNF-08** | La API debe utilizar rutas versionadas. |
| **RNF-09** | Las entradas deben validarse antes de ejecutar operaciones críticas. |
| **RNF-10** | Las operaciones empresariales compuestas deben preservar consistencia transaccional. |
| **RNF-11** | Los errores deben utilizar respuestas HTTP coherentes. |
| **RNF-12** | Las credenciales no deben almacenarse en el repositorio. |
| **RNF-13** | El proyecto debe poder compilarse mediante Maven. |
| **RNF-14** | Los límites modulares deben poder verificarse mediante pruebas. |
| **RNF-15** | La API debe estar documentada con OpenAPI. |
| **RNF-16** | El código debe mantener separación entre controller, service, repository, dto y entity. |
| **RNF-17** | La solución debe generar un único artefacto ejecutable `.jar`. |

---

# 45. Reglas de negocio

### RN-01 — Acceso modular

Un módulo no puede utilizar directamente el repositorio interno de otro módulo.

### RN-02 — Producto válido

Una operación que requiera un producto debe comprobar que el producto exista.

### RN-03 — Stock suficiente

Una venta no puede completarse si alguno de sus productos no dispone de stock suficiente.

### RN-04 — Conflicto por stock

El stock insuficiente debe producir una respuesta:

```http
409 Conflict
```

### RN-05 — Atomicidad de venta

Una venta y sus detalles deben registrarse como una única operación lógica.

### RN-06 — Integridad

No debe persistirse una venta parcialmente completada.

### RN-07 — Validación

Los datos inválidos deben rechazarse antes de ejecutar la lógica crítica.

### RN-08 — Encapsulamiento

Las entidades de persistencia no deben constituir automáticamente el contrato público de la API.

### RN-09 — Credenciales

Ninguna credencial real debe publicarse en GitHub.

---

# 46. Criterios de aceptación generales

Una funcionalidad se considera aceptada cuando:

- Compila correctamente.
- Respeta la arquitectura definida.
- No introduce dependencias modulares prohibidas.
- Persiste los datos de manera correcta.
- Valida los datos de entrada.
- Devuelve el código HTTP correspondiente.
- Maneja errores conocidos.
- No expone credenciales.
- La operación puede probarse desde un cliente REST/OpenAPI.
- Las pruebas de modularidad continúan aprobándose.
- La documentación refleja el comportamiento implementado.

---

# 47. Definition of Done

Una tarea se considera **Done** cuando:

- [ ] El código está implementado.
- [ ] El proyecto compila.
- [ ] La funcionalidad puede ejecutarse.
- [ ] Se respetan los módulos.
- [ ] No existe acceso indebido entre repositorios.
- [ ] Se utilizan DTO cuando corresponde.
- [ ] Las validaciones están implementadas.
- [ ] Los errores están controlados.
- [ ] Las transacciones están configuradas cuando corresponde.
- [ ] Los endpoints tienen respuestas HTTP correctas.
- [ ] Se verificó la persistencia en Oracle.
- [ ] Las pruebas relevantes pasan.
- [ ] No existen credenciales expuestas.
- [ ] Git no incluye `target/`.
- [ ] La documentación fue actualizada.
- [ ] El cambio está listo para subir al repositorio.

---

# 48. Riesgos técnicos

| Riesgo | Impacto | Mitigación |
|---|---|---|
| Acoplamiento entre módulos | Alto | Servicios públicos + Spring Modulith |
| Acceso cruzado a repositorios | Alto | Pruebas de modularidad |
| Errores de transacción | Alto | `@Transactional` y pruebas |
| Inconsistencia de stock | Alto | Validación previa + transacción |
| Diferencias entidad/BD | Medio/Alto | `ddl-auto=validate` |
| Credenciales publicadas | Alto | Variables de entorno + `.gitignore` |
| DTO mal definidos | Medio | Contratos explícitos |
| Endpoints inconsistentes | Medio | Convención `/api/v1` |
| Falta de documentación | Medio | OpenAPI + Markdown + ADR |
| Crecimiento desordenado | Alto | Arquitectura módulo→capas |

---

# 49. Entregables

El proyecto debe mantener como entregables principales:

- Código fuente.
- `pom.xml`.
- Configuración Spring.
- Docker Compose para desarrollo.
- Scripts SQL requeridos.
- Entidades.
- Repositorios.
- Servicios.
- DTO.
- Controllers.
- Manejo de errores.
- Pruebas.
- OpenAPI.
- ADR.
- `README.md`.
- `PROJECT_BRIEF.md`.
- Documentación complementaria por sesión.
- Evidencias de funcionamiento cuando sean requeridas académicamente.

---

# 50. Restricciones

1. Utilizar Java 21.
2. Utilizar Spring Boot 4.0.7 según la base definida para el proyecto.
3. Mantener un único proyecto Maven.
4. Mantener un único artefacto `.jar`.
5. Utilizar arquitectura modular.
6. Evitar acceso directo a repositorios de otros módulos.
7. Utilizar Oracle como base de datos.
8. No utilizar generación automática indiscriminada del esquema.
9. Utilizar `ddl-auto=validate`.
10. No publicar secretos.
11. No crear módulos o paquetes vacíos “por si acaso”.
12. Mantener la estructura indicada por la guía académica.
13. Incorporar funcionalidades progresivamente según las sesiones.

---

# 51. Estado actual resumido

```text
[OK] Entorno Java 21
[OK] Spring Boot
[OK] Maven
[OK] Oracle
[OK] Docker
[OK] Configuración OpenAPI
[OK] Módulo Catálogo
[OK] Categoría
[OK] Producto
[OK] Repository
[OK] Service
[OK] DTO de salida
[OK] Controllers REST
[OK] GET categorías
[OK] GET productos
[OK] Relación Categoría–Producto
[OK] Spring Modulith
[OK] ModularityTests
[EN PROGRESO / S04] Módulo Ventas
[EN PROGRESO / S04] Venta + DetalleVenta
[EN PROGRESO / S04] Transacciones
[EN PROGRESO / S04] Validación de stock
[PENDIENTE POR ROADMAP] Consultas y reportes
[PENDIENTE POR ROADMAP] Seguridad
```

---

# 52. Visión futura

BomERP debe evolucionar manteniendo sus límites modulares para incorporar progresivamente nuevos dominios empresariales.

Posible evolución:

```text
BomERP
│
├── Catálogo
│   ├── Categorías
│   └── Productos
│
├── Ventas
│   ├── Ventas
│   └── Detalles
│
├── Compras
│
├── Seguridad
│
└── Otros módulos futuros
```

La prioridad no es aumentar la cantidad de módulos rápidamente, sino mantener una arquitectura comprensible, comprobable y mantenible.

---

# 53. Principio rector del proyecto

> **BomERP debe crecer por funcionalidades reales, respetando los límites de cada módulo y evitando dependencias innecesarias.**

La arquitectura debe hacer posible que el sistema sea fácil de:

- Comprender.
- Probar.
- Modificar.
- Mantener.
- Extender.
- Documentar.

---

## Autoría académica

Proyecto desarrollado como parte del curso **Lenguaje de Programación II** de la carrera de **Ingeniería de Sistemas — Universidad Peruana Unión**.

---

## Nota sobre este documento

Este archivo funciona como **Project Brief técnico y funcional** del proyecto BomERP. Debe mantenerse actualizado a medida que se incorporen nuevas sesiones, módulos, reglas de negocio, endpoints o decisiones arquitectónicas.
