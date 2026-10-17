# Sistema de Control de Rescate y Adopción Animal

## 1. Introducción

El sistema permitirá registrar animales rescatados, administrar sus datos, gestionar solicitudes de adopción y realizar seguimiento de los procesos. Su propósito es organizar la información y facilitar el trabajo del personal encargado.

## 2. Actores del sistema

- **Administrador:** gestiona usuarios y supervisa el sistema.
- **Rescatista:** registra animales rescatados y actualiza su estado.
- **Adoptante:** consulta animales disponibles y presenta solicitudes de adopción.
- **Encargado de adopciones:** revisa solicitudes, aprueba o rechaza adopciones y registra el resultado.

## 3. Requerimientos funcionales

- RF01: Registrar, consultar, modificar y dar de baja lógica a los animales.
- RF02: Registrar los datos del rescate, incluyendo fecha, lugar y descripción.
- RF03: Consultar animales disponibles para adopción.
- RF04: Registrar solicitudes de adopción.
- RF05: Revisar, aprobar o rechazar solicitudes.
- RF06: Registrar la adopción y actualizar el estado del animal.
- RF07: Gestionar usuarios según sus roles.
- RF08: Consultar el historial de rescates y adopciones.

## 4. Requerimientos no funcionales

- RNF01: El sistema debe proteger los datos mediante autenticación y permisos por rol.
- RNF02: La interfaz debe ser clara y fácil de utilizar.
- RNF03: La información debe almacenarse de forma consistente.
- RNF04: El diseño debe facilitar el mantenimiento y la ampliación del sistema.
- RNF05: El sistema debe validar los datos antes de guardarlos.

## 5. Reglas de negocio

- Un animal debe estar registrado antes de recibir solicitudes de adopción.
- Solo los animales disponibles pueden ser adoptados.
- Una solicitud debe ser revisada por el encargado autorizado.
- Al completarse una adopción, el estado del animal cambia a Adoptado.
- Cada operación importante debe quedar registrada para facilitar el seguimiento.

## 6. Entidades principales

- Usuario: id, nombre, correo, contraseña cifrada y rol.
- Animal: id, nombre, especie, edad aproximada, descripción y estado.
- Rescate: id, fecha, lugar, descripción y responsable.
- SolicitudAdopcion: id, fecha, estado y observaciones.
- Adopcion: id, fecha, animal, adoptante y responsable.

## 7. Patrones de diseño propuestos

### Factory Method (creacional)
Se utilizará para crear distintos tipos de notificaciones sin acoplar el sistema a una clase concreta.

### Repository (estructural, según la clasificación utilizada en el curso)
Se utilizará para separar el acceso a los datos de la lógica del sistema. Nota: Repository suele considerarse un patrón arquitectónico, no uno de los patrones GoF.

### Observer (de comportamiento)
Se utilizará para notificar a los usuarios cuando cambie el estado de una solicitud o se complete una adopción.

## 8. Organización del proyecto

- docs/: análisis y documentación.
- diagrams/: diagramas UML y sus archivos fuente.
- src/: código fuente futuro del sistema.
- README.md: descripción general y guía del repositorio.

## 9. Control de versiones con Gitflow

- main: versión estable del proyecto.
- develop: integración de los avances.
- feature/analisis-sistema: desarrollo del análisis.
- feature/diagramas-uml: elaboración de los diagramas.
- feature/patrones-diseno: documentación de los patrones.

Cada avance se registrará mediante commits descriptivos y se integrará a develop mediante solicitudes de extracción cuando corresponda.

## 10. Conclusión

El análisis establece una base inicial para diseñar una solución organizada, segura y mantenible para el control de rescates y adopciones. Los requerimientos y patrones propuestos deberán validarse con el caso técnico oficial de la asignatura.
