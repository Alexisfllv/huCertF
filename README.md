# Historias de Usuario - Sistema de Registro de Solicitudes y Página Informativa

# Épica 1: Gestión de Solicitudes  
---
## Historia de Usuario 1.0: Configuración Inicial
**Descripción:**  
Como desarrollador, necesito configurar la base técnica del sistema para permitir la gestión eficiente de solicitudes.

#### Criterios de Aceptación:
1. La base de datos debe estar configurada con la tabla `solicitud`.
2. Los endpoints básicos de creación, lectura, actualización y eliminación (CRUD) deben estar disponibles.
3. El backend debe permitir solicitudes desde el frontend mediante CORS.
4. La estructura inicial del frontend debe estar lista para consumir los servicios del backend.
5. La API debe estar documentada con Swagger para facilitar la interacción y pruebas.

#### Tareas Técnicas:
- **Backend:**
  - Configurar el proyecto de Spring Boot con dependencias necesarias.
  - **Base de Datos:**
    - Crear la tabla `solicitud` con los siguientes campos:
      - `idSolicitud`: autoincremental.
      - `nombre`, `apellido`, `dirección`, `telefono`, `correo`, `tipo de servicio`, `descripción`: no nulos con longitud definida.
  - Implementar endpoints iniciales (POST, GET, PUT, DELETE) para la tabla `solicitud`.
  - Configurar CORS para solicitudes del frontend (`http://localhost:4200`).
  - **Swagger:**
    - Agregar dependencia de Swagger en el proyecto.
    - Configurar la documentación automática de los endpoints.
    - Verificar que Swagger UI esté disponible en el endpoint `/swagger-ui.html`.

- **Frontend:**
  - Crear modelo de solicitud con los campos a los de la tabla.
  - Crear servicio de solicitud que consuman los servicios del backend.

- **Validación:**
  - Probar que los endpoints CRUD funcionan correctamente con herramientas como Swagger UI y Postman.
  - Verificar que Swagger documente correctamente los endpoints disponibles.
  - Confirmar que el frontend puede comunicarse con el backend exitosamente.

---
## Historia de Usuario 1.1: Registrar Solicitud

**Descripción:**  
Como solicitante, quiero registrar una nueva solicitud ingresando datos como nombre, apellidos, dirección, teléfono, correo, tipo de servicio y descripción del problema, para que pueda ser procesada.

### Criterios de Aceptación:
1. El sistema valida los campos obligatorios antes de guardar.
2. Los datos se almacenan en la base de datos correctamente.
3. El campo "Tipo de Servicio" debe ser un menú desplegable (dropdown).
4. El usuario solo puede elegir entre las opciones: "Instalación", "Reparación", "Mantenimiento" y "Extras".
5. Se muestra un mensaje de confirmación tras un registro exitoso.

### Tareas Técnicas:
- **Backend:**
  - Implementar un endpoint POST en Spring Boot (`http://localhost:port/solicitudes`).

- **Frontend:**
  - Consumir metodo POST.
  - Configurar el dropdown con las opciones predefinidas.

- **Validación:**
  - Verificar que los campos obligatorios sean validados correctamente en el frontend.
  - Comprobar que el tipo de servicio tenga solo las opciones permitidas.

---

## Historia de Usuario 1.2: Listar Solicitudes

**Descripción:**  
Como recepcionista, quiero ver un listado de todas las solicitudes, para monitorear la información de ingreso.

### Criterios de Aceptación:
1. La lista muestra los campos clave: `idSolicitud`, `nombre`, `apellido`, `dirección`, `telefono`, `correo`, `tipo de servicio`, `descripción`, y opciones de editar/eliminar.
2. La interfaz permite paginar.
3. La interfaz permite buscar según datos de la columna.

### Tareas Técnicas:
- **Backend:**
  - Implementar un endpoint GET para obtener todas las solicitudes (`http://localhost:port/solicitudes`).

- **Frontend:**
  - Configurar la interfaz para mostrar la lista de solicitudes.
  - Añadir paginación y filtros de búsqueda.

- **Validación:**
  - Verificar que los datos se muestren correctamente en la interfaz.
  - Asegurarse de que la paginación y búsqueda funcionen según lo esperado.

---

## Historia de Usuario 1.3: Actualizar Solicitud

**Descripción:**  
Como recepcionista, quiero poder editar una solicitud existente, para corregir errores o actualizar información.

### Criterios de Aceptación:
1. El sistema permite modificar los campos de una solicitud seleccionada.
2. Los datos actualizados se guardan correctamente en la base de datos.
3. Se muestra un mensaje de confirmación tras una actualización exitosa.

### Tareas Técnicas:
- **Backend:**
  - Implementar un endpoint PUT para actualizar solicitudes (`http://localhost:port/solicitudes`).

- **Frontend:**
  - Agregar un botón de "Editar" en cada fila del listado de solicitudes.
  - Crear un formulario editable con los datos precargados de la solicitud seleccionada.
  - Conectar el formulario de edición al backend.

- **Validación:**
  - Asegurarse de que los datos se actualicen correctamente en la base de datos.
  - Verificar que el mensaje de confirmación se muestre tras la actualización.
---
## Historia de Usuario 1.4: Eliminar Solicitud

**Descripción:**  
Como usuario, quiero poder eliminar una solicitud registrada, para gestionar correctamente el flujo de trabajo y mantener actualizada la base de datos.

### Criterios de Aceptación:
1. El sistema debe solicitar confirmación antes de eliminar una solicitud.
2. Una vez eliminada, la solicitud debe desaparecer del listado de solicitudes.
3. El sistema debe mostrar un mensaje indicando que la solicitud fue eliminada correctamente.


### Tareas Técnicas:

- **Backend:**
  - Implementar un endpoint DELETE para actualizar solicitudes (`http://localhost:port/solicitudes/{id}`).

- **Frontend:**
  - Agregar un botón de "Eliminar" en cada fila del listado de solicitudes.
  - Conectar el formulario de eliminar al backend.

- **Validación:**
  - Probar que la solicitud se elimina correctamente desde la base de datos.
  - Asegurarse de que el mensaje de confirmación se encuentre.
  - Verificar que no se encuentre la solicitud eliminada.
---
# Épica 2: Gestión de Citas
---
## Historia de Usuario 2.0: Configuración Inicial  
**Descripción:**  
Como desarrollador, necesito configurar la base técnica del sistema para permitir la gestión eficiente de citas.

### Criterios de Aceptación:  
1. La base de datos debe estar configurada con la tabla `cita`.
2. Los endpoints básicos de creación, lectura, actualización y eliminación (CRUD) deben estar disponibles.
3. El backend debe permitir solicitudes desde el frontend mediante CORS.
4. La estructura inicial del frontend debe estar lista para consumir los servicios del backend.
5. La API debe estar documentada con Swagger para facilitar la interacción y pruebas.

### Tareas Técnicas:  
- **Backend:**
  - Configurar el proyecto de Spring Boot con dependencias necesarias.
  - **Base de Datos:**
    - Crear la tabla `cita` con los siguientes campos:
      - `idCita`: autoincremental.
      - `nombre`, `apellido`, `telefono`, `direccion`, `tipoServicio`, `descripcion`, `nombreTecnico`: no nulos con longitud definida.
  - Implementar endpoints iniciales (POST, GET, PUT, DELETE) para la tabla `cita`.
  - Configurar CORS para solicitudes del frontend (`http://localhost:4200`).
  - **Swagger:**
    - Agregar dependencia de Swagger en el proyecto.
    - Configurar la documentación automática de los endpoints.
    - Verificar que Swagger UI esté disponible en el endpoint `/swagger-ui.html`.

- **Frontend:**
  - Crear modelo de cita con los campos de la tabla.
  - Crear servicio de cita que consuma los servicios del backend.

- **Validación:**
  - Probar que los endpoints CRUD funcionan correctamente con herramientas como Swagger UI y Postman.
  - Verificar que Swagger documente correctamente los endpoints disponibles.
  - Confirmar que el frontend puede comunicarse con el backend exitosamente.

---

## Historia de Usuario 2.1: Registrar Cita  

**Descripción:**  
Como recepcionista, quiero registrar una nueva cita ingresando datos como nombre, apellidos, teléfono, dirección, tipo de servicio, descripción y nombre del técnico asignado, para que pueda ser procesada.

### Criterios de Aceptación:  
1. El sistema valida los campos obligatorios antes de guardar.
2. Los datos se almacenan en la base de datos correctamente.
3. El campo "Tipo de Servicio" debe ser un menú desplegable (dropdown).
4. El usuario solo puede elegir entre las opciones: "Instalación", "Reparación", "Mantenimiento" y "Extras".
5. Se muestra un mensaje de confirmación tras un registro exitoso.

### Tareas Técnicas:  
- **Backend:**
  - Implementar un endpoint POST en Spring Boot (`http://localhost:port/citas`).

- **Frontend:**
  - Consumir método POST.
  - Configurar el dropdown con las opciones predefinidas.

- **Validación:**
  - Verificar que los campos obligatorios sean validados correctamente en el frontend.
  - Comprobar que el tipo de servicio tenga solo las opciones permitidas.

---

## Historia de Usuario 2.2: Listar Citas  

**Descripción:**  
Como recepcionista, quiero ver un listado de todas las citas, para monitorear la información de ingreso.

### Criterios de Aceptación:  
1. La lista muestra los campos clave: `idCita`, `nombre`, `apellido`, `telefono`, `direccion`, `tipoServicio`, `descripcion`, `nombreTecnico`, y opciones de editar/eliminar.
2. La interfaz permite paginar.
3. La interfaz permite buscar según datos de la columna.

### Tareas Técnicas:  
- **Backend:**
  - Implementar un endpoint GET para obtener todas las citas (`http://localhost:port/citas`).

- **Frontend:**
  - Configurar la interfaz para mostrar la lista de citas.
  - Añadir paginación y filtros de búsqueda.

- **Validación:**
  - Verificar que los datos se muestren correctamente en la interfaz.
  - Asegurarse de que la paginación y búsqueda funcionen según lo esperado.

---

## Historia de Usuario 2.3: Actualizar Cita  

**Descripción:**  
Como recepcionista, quiero poder editar una cita existente, para corregir errores o actualizar información.

### Criterios de Aceptación:  
1. El sistema permite modificar los campos de una cita seleccionada.
2. Los datos actualizados se guardan correctamente en la base de datos.
3. Se muestra un mensaje de confirmación tras una actualización exitosa.

### Tareas Técnicas:  
- **Backend:**
  - Implementar un endpoint PUT para actualizar citas (`http://localhost:port/citas`).

- **Frontend:**
  - Agregar un botón de "Editar" en cada fila del listado de citas.
  - Crear un formulario editable con los datos precargados de la cita seleccionada.
  - Conectar el formulario de edición al backend.

- **Validación:**
  - Asegurarse de que los datos se actualicen correctamente en la base de datos.
  - Verificar que el mensaje de confirmación se muestre tras la actualización.

---

## Historia de Usuario 2.4: Eliminar Cita  

**Descripción:**  
Como recepcionista, quiero poder eliminar una cita registrada, para gestionar correctamente el flujo de trabajo y mantener actualizada la base de datos.

### Criterios de Aceptación:  
1. El sistema debe solicitar confirmación antes de eliminar una cita.
2. Una vez eliminada, la cita debe desaparecer del listado de citas.
3. El sistema debe mostrar un mensaje indicando que la cita fue eliminada correctamente.

### Tareas Técnicas:  
- **Backend:**
  - Implementar un endpoint DELETE para eliminar citas (`http://localhost:port/citas/{id}`).

- **Frontend:**
  - Agregar un botón de "Eliminar" en cada fila del listado de citas.
  - Conectar el botón de eliminar al backend.

- **Validación:**
  - Probar que la cita se elimina correctamente desde la base de datos.
  - Asegurarse de que el mensaje de confirmación se muestre.
  - Verificar que no se encuentre la cita eliminada en el listado.
---
# Épica 3: Desarrollo del Menú Principal y Secciones de la Página Web

**Descripción:**  
El objetivo de esta épica es crear el menú principal y las secciones de la página web, que incluirán el logo de la empresa, las secciones de "Servicios", "Nosotros", y "Solicitar Servicio". Todo se implementará usando HTML y CSS.

---
## Historia de Usuario 3.1: Menú Principal
**Descripción:**  
Como visitante de la página web, quiero ver el logo de la empresa y un menú que me permita acceder a las secciones de "Servicios", "Nosotros" y "Solicitar Servicio", para navegar fácilmente por el sitio y conocer la empresa.

### Criterios de Aceptación:
1. El logo debe ser visible en la parte superior de todas las páginas y redirigir al inicio al hacer clic.
2. El menú debe contener enlaces a las secciones de "Servicios", "Nosotros" y "Solicitar Servicio".
3. La página debe incluir una breve descripción de la empresa en la página principal.

### Tareas Técnicas:
- **HTML:**
  - `code`
  
- **CSS:**
  - Estilizar el logo para que se vea correctamente en la parte superior.
  - Crear estilos para el menú de navegación y asegurar que los enlaces estén destacados.
  - Estilizar la sección de la descripción breve para hacerla atractiva.

---

## Historia de Usuario 3.2: Ver Sección de Servicios
**Descripción:**  
Como usuario, quiero acceder a la sección de "Servicios", donde se muestren las opciones disponibles como instalación, reparaciones, mantenimiento y servicios adicionales, para saber qué ofrece la empresa.

### Criterios de Aceptación:
1. La sección debe listar los servicios disponibles con descripciones breves.
2. Los usuarios deben poder ver detalles adicionales sobre cada servicio si lo desean.

### Tareas Técnicas:
- **HTML:**
  - `code`

- **CSS:**
  - Estilizar los elementos para que cada servicio se vea bien estructurado.
  - Asegurar que la página sea responsive, es decir, que se vea bien en dispositivos móviles.

---

## Historia de Usuario 3.3: Ver Sección de Nosotros
**Descripción:**  
Como usuario, quiero acceder a la sección "Nosotros", donde pueda conocer la historia, misión, visión y datos de contacto de la empresa, para entender mejor su identidad y cómo contactar.

### Criterios de Aceptación:
1. La página debe contener información clara sobre la historia, misión, visión y contacto de la empresa.
2. La información de contacto debe ser fácilmente visible.

### Tareas Técnicas:
- **HTML:**
  - 

- **CSS:**
  - Estilizar las secciones para que cada una tenga un diseño limpio y agradable.
  - Asegurarse de que los datos de contacto sean fácilmente accesibles y visibles.

---

## Historia de Usuario 3.4: Solicitar Servicio
**Descripción:**  
Como usuario que necesita un servicio, quiero acceder a la sección "Solicitar Servicio", donde pueda ver una presentación con los detalles del servicio y un botón para solicitarlo, para que sea fácil completar mi solicitud.

### Criterios de Aceptación:
1. La página debe mostrar información básica sobre cómo solicitar un servicio.
2. Debe haber un botón visible para enviar una solicitud de servicio.

### Tareas Técnicas:
- **HTML:**
  - `code`

- **CSS:**
  - Estilizar el formulario para que sea fácil de completar.
  - Asegurarse de que el botón de "Solicitar Servicio" sea prominente y fácil de encontrar.

