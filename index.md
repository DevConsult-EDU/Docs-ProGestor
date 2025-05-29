# Docs-ProGestor

## Sistema de Gestión de Proyectos “ProGestor”

### Contexto del Proyecto

#### La Empresa

DevConsult S.L. es una consultora tecnológica emergente dedicada a proporcionar servicios de desarrollo de software a pequeñas y medianas empresas. Tras un análisis de mercado, han identificado que muchas consultoras pequeñas carecen de herramientas digitales asequibles para gestionar sus proyectos, clientes y tareas de forma eficiente.

#### El Problema

Las consultoras tecnológicas actualmente gestionan sus proyectos y clientes de forma manual o con sistemas anticuados, lo que provoca:

- Dificultad para hacer seguimiento del estado de los proyectos
- Problemas para asignar tareas y gestionar recursos
- Falta de visibilidad sobre la cartera de clientes
- Dificultad para medir la rentabilidad de cada proyecto

#### La Solución: ProGestor

Se propone desarrollar “ProGestor”, una aplicación web que permita a las consultoras:
- Gestionar usuarios (tanto personal interno como clientes)
- Crear y gestionar proyectos de forma digital
- Asignar y hacer seguimiento de tareas dentro de cada proyecto
- Tener un sistema de autenticación seguro
- Obtener datos básicos sobre el estado de sus proyectos

### Alcance del Proyecto para Prácticas

Como estudiante en prácticas, desarrollarás una versión simplificada pero funcional del sistema, que servirá como prueba de concepto. Esta versión incluirá:

- **Backend con Laravel 11:** API RESTful que gestione la lógica de negocio y los datos
- **Frontend con Angular:** Interfaz de usuario intuitiva y responsive usando Tailwind CSS
- **Autenticación con JWT:** Sistema seguro para validar usuarios
- **Tres módulos CRUD completos:** Gestión de usuarios, gestión de clientes, gestión de proyectos y gestión de tareas

### Importancia del SRP (Principio de Responsabilidad Única)

En este proyecto aplicaremos el Principio de Responsabilidad Única, uno de los cinco principios SOLID fundamentales en el desarrollo de software. Este principio establece que:
> “Una clase debe tener una, y solo una, razón para cambiar”

#### ¿Por qué es importante para este proyecto?

- **Mantenibilidad:** Código más fácil de entender y modificar
- **Testabilidad:** Facilita las pruebas unitarias y de integración
- **Reutilización:** Componentes con responsabilidades claras son más reutilizables
- **Escalabilidad:** Más sencillo añadir nuevas funcionalidades sin afectar a las existentes

Al aplicar SRP, cada controlador en Laravel y cada servicio en Angular tendrán una única responsabilidad, lo que hará el código más limpio, mantenible y profesional.

### Beneficios del Testing

En este proyecto daremos especial importancia al testing del backend por varias razones:

- **Garantía de calidad:** Verificar que cada parte del sistema funciona como se espera
- **Documentación viva:** Los tests sirven como documentación de cómo debe comportarse el sistema
- **Refactorización segura:** Poder modificar el código con la confianza de que no se rompe la funcionalidad
- **Desarrollo ágil:** Facilita la implementación de cambios y nuevas características

### Modelo de Datos Simplificado

#### Usuario
- **ID**
- **Nombre**
- **Email**
- **Contraseña**
- **Rol** (administrador/usuario normal)
- **Fecha de creación**
- **Fecha de actualización**

#### Cliente
- **ID**
- **Nombre**
- **Email**
- **Teléfono**
- **Dirección**
- **Fecha de creación**
- **Fecha de actualización**

#### Proyecto
- **ID**
- **Nombre**
- **Descripción**
- **ID Cliente** (a quién pertenece el proyecto)
- **Estado** (pendiente/en progreso/completado/cancelado)
- **Fecha de inicio**
- **Fecha de finalización**
- **Fecha de creación**
- **Fecha de actualización**

#### Tarea
- **ID**
- **ID Proyecto** (a qué proyecto pertenece)
- **Título**
- **Descripción**
- **Estado** (pendiente/en progreso/completada)
- **Prioridad** (baja/media/alta)
- **ID Usuario** (quién debe realizar la tarea)
- **Fecha de creación**
- **Fecha de actualización**

### Historias de Usuario Básicas

- *Como administrador, quiero poder registrarme e iniciar sesión para acceder al sistema*
- *Como administrador, quiero poder crear, ver, editar y eliminar usuarios*
- *Como administrador, quiero poder crear, ver, editar y eliminar clientes*
- *Como administrador, quiero poder crear, ver, editar y eliminar proyectos*
- *Como administrador, quiero poder crear, ver, editar y eliminar tareas*
- *Como usuario, quiero poder registrarme e iniciar sesión en el sistema*
- *Como usuario, quiero poder ver mis proyectos asignados*
- *Como usuario, quiero poder ver y actualizar mis tareas asignadas*

### Listado de Tareas del Proyecto

#### BACKEND (Laravel 11)

##### Configuración inicial
- Instalar Laravel 11
- Configurar la base de datos MySQL
- Instalar paquete JWT para autenticación

##### Base de datos
- Crear migración para tabla Usuarios
- Crear migración para tabla Clientes
- Crear migración para tabla Proyectos
- Crear migración para tabla Tareas
- Crear los modelos básicos (Usuario, Cliente, Proyecto, Tarea)

##### Autenticación (SRP)
- Configurar JWT
- Crear `LoginController` (responsabilidad única: gestionar login)
- Crear `RegisterController` (responsabilidad única: gestionar registro)
- Crear `LogoutController` (responsabilidad única: gestionar cierre de sesión)

##### CRUD de Usuarios (SRP)
- Crear `IndexUserController` (responsabilidad única: listar usuarios)
- Crear `ShowUserController` (responsabilidad única: mostrar detalle de usuario)
- Crear `StoreUserController` (responsabilidad única: crear usuario)
- Crear `UpdateUserController` (responsabilidad única: actualizar usuario)
- Crear `DeleteUserController` (responsabilidad única: eliminar usuario)

##### CRUD de Clientes (SRP)
- Crear `IndexClientController` (responsabilidad única: listar clientes)
- Crear `ShowClientController` (responsabilidad única: mostrar detalle de cliente)
- Crear `StoreClientController` (responsabilidad única: crear cliente)
- Crear `UpdateClientController` (responsabilidad única: actualizar cliente)
- Crear `DeleteClientController` (responsabilidad única: eliminar cliente)

##### CRUD de Proyectos (SRP)
- Crear `IndexProjectController` (responsabilidad única: listar proyectos)
- Crear `ShowProjectController` (responsabilidad única: mostrar detalle de proyecto)
- Crear `StoreProjectController` (responsabilidad única: crear proyecto)
- Crear `UpdateProjectController` (responsabilidad única: actualizar proyecto)
- Crear `DeleteProjectController` (responsabilidad única: eliminar proyecto)

##### CRUD de Tareas (SRP)
- Crear `IndexTaskController` (responsabilidad única: listar tareas)
- Crear `ShowTaskController` (responsabilidad única: mostrar detalle de tarea)
- Crear `StoreTaskController` (responsabilidad única: crear tarea)
- Crear `UpdateTaskController` (responsabilidad única: actualizar tarea)
- Crear `DeleteTaskController` (responsabilidad única: eliminar tarea)

##### Testing Backend
- Crear test para `LoginController` (Feature test)
- Crear test para `RegisterController` (Feature test)
- Crear test para `LogoutController` (Feature test)
- Crear test para `IndexUserController` (Feature test)
- Crear test para `StoreUserController` (Feature test)
- Crear test para `UpdateUserController` (Feature test)
- Crear test para `DeleteUserController` (Feature test)
- Crear test para `IndexClientController` (Feature test)
- Crear test para `StoreClientController` (Feature test)
- Crear test para `IndexProjectController` (Feature test)
- Crear test para `StoreProjectController` (Feature test)
- Crear test para `IndexTaskController` (Feature test)
- Crear test para `StoreTaskController` (Feature test)
- Crear test para `UpdateTaskController` (Feature test)
- Crear test unitario para validación de Proyecto
- Crear test unitario para validación de Tarea

#### FRONTEND (Angular)

##### Configuración inicial
- Instalar Angular
- Instalar Tailwind CSS
- Configurar conexión con API

##### Autenticación (SRP)
- Crear `LoginService` (responsabilidad única: gestionar login)
- Crear `RegisterService` (responsabilidad única: gestionar registro)
- Crear `TokenService` (responsabilidad única: gestionar token JWT)
- Crear página de login
- Crear página de registro
- Configurar interceptor para JWT

##### Gestión de usuarios (SRP)
- Crear `UserListService` (responsabilidad única: obtener lista de usuarios)
- Crear `UserDetailService` (responsabilidad única: obtener detalle de usuario)
- Crear `UserCreateService` (responsabilidad única: crear usuario)
- Crear `UserUpdateService` (responsabilidad única: actualizar usuario)
- Crear `UserDeleteService` (responsabilidad única: eliminar usuario)
- Crear página de listado de usuarios
- Crear página de detalle de usuario
- Crear formulario para crear usuario
- Crear formulario para editar usuario
- Implementar eliminación de usuarios

##### Gestión de clientes (SRP)
- Crear `ClientListService` (responsabilidad única: obtener lista de clientes)
- Crear `ClientDetailService` (responsabilidad única: obtener detalle de cliente)
- Crear `ClientCreateService` (responsabilidad única: crear cliente)
- Crear `ClientUpdateService` (responsabilidad única: actualizar cliente)
- Crear `ClientDeleteService` (responsabilidad única: eliminar cliente)
- Crear página de listado de clientes
- Crear página de detalle de cliente
- Crear formulario para crear cliente
- Crear formulario para editar cliente
- Implementar eliminación de clientes

##### Gestión de proyectos (SRP)
- Crear `ProjectListService` (responsabilidad única: obtener lista de proyectos)
- Crear `ProjectDetailService` (responsabilidad única: obtener detalle de proyecto)
- Crear `ProjectCreateService` (responsabilidad única: crear proyecto)
- Crear `ProjectUpdateService` (responsabilidad única: actualizar proyecto)
- Crear `ProjectDeleteService` (responsabilidad única: eliminar proyecto)
- Crear página de listado de proyectos
- Crear página de detalle de proyecto
- Crear formulario para crear proyecto
- Crear formulario para editar proyecto
- Implementar eliminación de proyectos

##### Gestión de tareas (SRP)
- Crear `TaskListService` (responsabilidad única: obtener lista de tareas)
- Crear `TaskDetailService` (responsabilidad única: obtener detalle de tarea)
- Crear `TaskCreateService` (responsabilidad única: crear tarea)
- Crear `TaskUpdateService` (responsabilidad única: actualizar tarea)
- Crear `TaskDeleteService` (responsabilidad única: eliminar tarea)
- Crear página de listado de tareas
- Crear página de detalle de tarea
- Crear formulario para crear tarea
- Crear formulario para editar tarea
- Implementar eliminación de tareas

##### Detalles finales
- Añadir menú de navegación con Tailwind
- Mejorar diseño con componentes de Tailwind
- Realizar pruebas finales

---

## FUNCIONALIDADES ADICIONALES

### TimeEntry para Tareas

#### Contexto
Las consultoras necesitan registrar el tiempo dedicado a cada tarea para gestionar la productividad y facilitar la facturación a clientes.

#### El Problema
Actualmente no existe forma de registrar cuánto tiempo dedica cada usuario a las tareas asignadas, lo que impide:
- Medir la eficiencia en la ejecución de tareas
- Calcular costes reales de los proyectos
- Facturar con precisión a los clientes el tiempo dedicado

#### La Solución: TimeEntry en ProGestor
Se ampliará “ProGestor” para incluir:
- Registro de tiempo dedicado a cada tarea
- Visualización del tiempo acumulado por tarea y por proyecto
- Base para futura funcionalidad de facturación

#### Modelo de Datos Adicional: TimeEntry
- **ID**
- **ID Tarea**
- **ID Usuario**
- **Fecha**
- **Minutos**
- **Descripción**
- **Fecha de creación**
- **Fecha de actualización**

#### Listado de Tareas Adicionales del Proyecto (agrupadas por funcionalidad)

##### Estructura Inicial:
- Crear migración para tabla `TimeEntries`
- Crear modelo `TimeEntry` con relaciones a `Usuario` y `Tarea`
- Definir rutas API para los controladores de `TimeEntry`

##### Funcionalidad: Listar TimeEntries de una Tarea
- **BACKEND:** Crear `IndexTaskTimeEntryController` (responsabilidad única: listar time entries de una tarea)
- **FRONTEND:** Crear `TaskTimeEntryListService` (responsabilidad única: obtener time entries por tarea)
- **FRONTEND:** Crear componente de listado de time entries
- **FRONTEND:** Actualizar página de detalle de tarea para mostrar time entries
- **TEST:** Crear test para `IndexTaskTimeEntryController` (Feature test)

##### Funcionalidad: Ver Detalle de TimeEntry
- **BACKEND:** Crear `ShowTimeEntryController` (responsabilidad única: mostrar detalle de time entry)
- **FRONTEND:** Crear `TimeEntryDetailService` (responsabilidad única: obtener detalle de time entry)
- **FRONTEND:** Ampliar componente de listado para mostrar detalles al seleccionar
- **TEST:** Crear test para `ShowTimeEntryController` (Feature test)

##### Funcionalidad: Crear TimeEntry
- **BACKEND:** Crear `StoreTimeEntryController` (responsabilidad única: crear time entry)
- **FRONTEND:** Crear `TimeEntryCreateService` (responsabilidad única: crear time entry)
- **FRONTEND:** Crear componente de formulario para añadir time entry
- **FRONTEND:** Integrar formulario de creación en la vista de tarea
- **TEST:** Crear test para `StoreTimeEntryController` (Feature test)

##### Funcionalidad: Actualizar TimeEntry
- **BACKEND:** Crear `UpdateTimeEntryController` (responsabilidad única: actualizar time entry)
- **FRONTEND:** Crear `TimeEntryUpdateService` (responsabilidad única: actualizar time entry)
- **FRONTEND:** Crear componente de formulario para editar time entry
- **FRONTEND:** Integrar formulario de edición en la vista de detalle
- **TEST:** Crear test para `UpdateTimeEntryController` (Feature test)

##### Funcionalidad: Eliminar TimeEntry
- **BACKEND:** Crear `DeleteTimeEntryController` (responsabilidad única: eliminar time entry)
- **FRONTEND:** Crear `TimeEntryDeleteService` (responsabilidad única: eliminar time entry)
- **FRONTEND:** Añadir botones de eliminación en la vista de listado y detalle
- **FRONTEND:** Implementar confirmación antes de eliminar
- **TEST:** Crear test para `DeleteTimeEntryController` (Feature test)

##### Finalización
- Verificar integración con módulo de Tareas existente
- Probar flujo completo de TimeEntry
- Aplicar estilos con Tailwind CSS para mantener consistencia visual

---

### Comentarios en Tareas

#### Contexto
Para mejorar la comunicación y seguimiento, los usuarios necesitan poder dejar comentarios en las tareas, lo que facilitará el intercambio de información entre los miembros del equipo.

#### El Problema
Actualmente no hay forma de que los usuarios puedan comunicarse o dejar notas directamente en las tareas, lo que obliga a:
- Usar canales externos como correo o mensajería
- Perder información importante que queda fuera del sistema
- Dificultar el seguimiento del histórico de decisiones sobre una tarea

#### La Solución: Comentarios en ProGestor
Se ampliará “ProGestor” para incluir:
- Sistema de comentarios directamente asociados a cada tarea
- Visualización cronológica de los comentarios
- Asociación de cada comentario con el usuario que lo creó

#### Modelo de Datos Adicional: Comment
- **ID**
- **ID Tarea**
- **ID Usuario**
- **Contenido**
- **Fecha de creación**
- **Fecha de actualización**

#### Listado de Tareas Adicionales del Proyecto (agrupadas por funcionalidad)

##### Estructura Inicial
- Crear migración para tabla `Comments`
- Crear modelo `Comment` con relaciones a `Usuario` y `Tarea`
- Definir rutas API para los controladores de `Comment`

##### Funcionalidad: Listar Comentarios de una Tarea
- **BACKEND:** Crear `IndexTaskCommentController` (responsabilidad única: listar comentarios de una tarea)
- **FRONTEND:** Crear `TaskCommentListService` (responsabilidad única: obtener comentarios de una tarea)
- **FRONTEND:** Crear componente de listado de comentarios
- **FRONTEND:** Actualizar página de detalle de tarea para mostrar comentarios
- **TEST:** Crear test para `IndexTaskCommentController` (Feature test)

##### Funcionalidad: Crear Comentario
- **BACKEND:** Crear `StoreTaskCommentController` (responsabilidad única: crear comentario)
- **FRONTEND:** Crear `CommentCreateService` (responsabilidad única: crear comentario)
- **FRONTEND:** Crear componente de formulario para añadir comentario
- **FRONTEND:** Integrar formulario de creación en la vista de tarea
- **TEST:** Crear test para `StoreTaskCommentController` (Feature test)

##### Funcionalidad: Eliminar Comentario
- **BACKEND:** Crear `DeleteCommentController` (responsabilidad única: eliminar comentario)
- **FRONTEND:** Crear `CommentDeleteService` (responsabilidad única: eliminar comentario)
- **FRONTEND:** Añadir botones de eliminación en los comentarios (sólo para el autor y administradores)
- **FRONTEND:** Implementar confirmación antes de eliminar
- **TEST:** Crear test para `DeleteCommentController` (Feature test)

---

### Adjuntos en Tareas

#### Contexto
Los usuarios necesitan poder adjuntar archivos relevantes directamente a las tareas, como documentación, capturas de pantalla o cualquier otro material que facilite la comprensión y ejecución del trabajo.

#### El Problema
Actualmente no existe forma de asociar archivos a las tareas en el sistema, lo que provoca:
- Dispersión de la información en diferentes sistemas y carpetas
- Dificultad para encontrar documentación relevante para una tarea
- Pérdida de tiempo en la búsqueda de archivos asociados a una tarea
- Falta de contexto visual o documental que puede ser crucial para completar el trabajo

#### La Solución: Adjuntos en ProGestor
Se ampliará “ProGestor” para incluir:
- Sistema de adjuntos (attachments) directamente asociados a cada tarea
- Capacidad para subir, descargar y eliminar archivos
- Visualización de los archivos en la página de detalle de la tarea

#### Modelo de Datos Adicional: Attachment
- **ID**
- **ID Tarea**
- **ID Usuario** (quién sube el archivo)
- **Nombre original del archivo**
- **Nombre en el sistema** (evitar colisiones)
- **Tipo MIME**
- **Tamaño en bytes**
- **Ruta de almacenamiento**
- **Fecha de creación**
- **Fecha de actualización**

#### Listado de Tareas Adicionales del Proyecto (agrupadas por funcionalidad)

##### Estructura Inicial
- Crear migración para tabla `Attachments`
- Crear modelo `Attachment` con relaciones a `Usuario` y `Tarea`
- Configurar almacenamiento de archivos en Laravel
- Definir rutas API para los controladores de `Attachment`

##### Funcionalidad: Listar Adjuntos de una Tarea
- **BACKEND:** Crear `IndexTaskAttachmentController` (responsabilidad única: listar adjuntos de una tarea)
- **FRONTEND:** Crear `TaskAttachmentListService` (responsabilidad única: obtener adjuntos de una tarea)
- **FRONTEND:** Crear componente de listado de adjuntos
- **FRONTEND:** Actualizar página de detalle de tarea para mostrar adjuntos
- **TEST:** Crear test para `IndexTaskAttachmentController` (Feature test)

##### Funcionalidad: Subir Adjunto
- **BACKEND:** Crear `StoreTaskAttachmentController` (responsabilidad única: subir y almacenar adjunto)
- **FRONTEND:** Crear `AttachmentUploadService` (responsabilidad única: subir adjunto)
- **FRONTEND:** Crear componente de formulario para subir adjunto
- **FRONTEND:** Integrar formulario de subida en la vista de tarea
- **TEST:** Crear test para `StoreTaskAttachmentController` (Feature test)

##### Funcionalidad: Descargar Adjunto
- **BACKEND:** Crear `DownloadAttachmentController` (responsabilidad única: servir adjunto para descarga)
- **FRONTEND:** Crear `AttachmentDownloadService` (responsabilidad única: descargar adjunto)
- **FRONTEND:** Añadir botones de descarga en el listado de adjuntos
- **TEST:** Crear test para `DownloadAttachmentController` (Feature test)

##### Funcionalidad: Eliminar Adjunto
- **BACKEND:** Crear `DeleteAttachmentController` (responsabilidad única: eliminar adjunto)
- **FRONTEND:** Crear `AttachmentDeleteService` (responsabilidad única: eliminar adjunto)
- **FRONTEND:** Añadir botones de eliminación en el listado de adjuntos
- **FRONTEND:** Implementar confirmación antes de eliminar
- **TEST:** Crear test para `DeleteAttachmentController` (Feature test)

---

### Dashboard Simple

#### Contexto
Los usuarios necesitan una página de inicio que muestre de un vistazo la información más importante al entrar al sistema.

#### El Problema
Al iniciar sesión, los usuarios no tienen una visión inmediata de sus tareas y proyectos, debiendo navegar entre secciones para encontrar información relevante.

#### La Solución: Dashboard Básico en ProGestor
Se añadirá un dashboard sencillo que mostrará:
- Tareas pendientes del usuario
- Proyectos en los que participa
- Actividad reciente

#### Listado de Tareas Adicionales del Proyecto

##### Estructura Inicial
- Crear rutas API separadas para cada componente del dashboard
- Crear controladores específicos para cada responsabilidad

##### Funcionalidad: Tareas Pendientes del Usuario
- **BACKEND:** Crear `UserPendingTasksController` (responsabilidad única: obtener tareas pendientes del usuario)
- **FRONTEND:** Crear `UserPendingTasksService` (responsabilidad única: obtener tareas pendientes)
- **FRONTEND:** Crear componente de tareas pendientes
- **TEST:** Crear test para `UserPendingTasksController` (Feature test)

##### Funcionalidad: Proyectos Activos del Usuario
- **BACKEND:** Crear `UserActiveProjectsController` (responsabilidad única: obtener proyectos activos del usuario)
- **FRONTEND:** Crear `UserActiveProjectsService` (responsabilidad única: obtener proyectos activos)
- **FRONTEND:** Crear componente de proyectos activos
- **TEST:** Crear test para `UserActiveProjectsController` (Feature test)

##### Funcionalidad: Actividad Reciente
- **BACKEND:** Crear `RecentActivitiesController` (responsabilidad única: obtener actividad reciente)
- **FRONTEND:** Crear `RecentActivitiesService` (responsabilidad única: obtener actividad reciente)
- **FRONTEND:** Crear componente de actividad reciente
- **TEST:** Crear test para `RecentActivitiesController` (Feature test)

##### Página de Dashboard
- **FRONTEND:** Crear `DashboardComponent` (responsabilidad única: integrar los tres componentes anteriores)
- **FRONTEND:** Configurar ruta para que Dashboard sea la página inicial tras login

---

### Gestión de Notificaciones con Eventos y Handlers

#### Contexto
Los usuarios necesitan estar informados sobre eventos importantes que ocurren en el sistema, como asignaciones de tareas, comentarios nuevos o fechas límite próximas, para poder responder oportunamente.

#### El Problema
Actualmente los usuarios deben revisar manualmente las tareas y proyectos para enterarse de novedades, lo que provoca:
- Retrasos en responder a eventos importantes
- Olvido de tareas pendientes
- Falta de visibilidad sobre la actividad del equipo
- Comunicación ineficiente dentro del proyecto

#### La Solución: Sistema de Notificaciones con Eventos en ProGestor
Se implementará un sistema de notificaciones basado en eventos, donde cada acción relevante dispara un evento que será capturado por listeners específicos que crearán las notificaciones correspondientes.

#### Modelo de Datos Adicional: Notification
- **ID**
- **ID Usuario** (destinatario)
- **Tipo** (asignación, comentario, fecha límite, etc.)
- **Título** (texto descriptivo breve)
- **Contenido** (texto detallado de la notificación)
- **Enlace** (URL a la que dirigirse al hacer clic)
- **Leída** (booleano)
- **Fecha de creación**
- **Fecha de actualización**

#### Listado de Tareas Adicionales del Proyecto

##### BACKEND (Laravel 11)
###### Base de datos
- Crear migración para tabla `Notifications`
- Crear modelo `Notification` con relación a `Usuario`

###### CRUD de Notificaciones (SRP)
- Crear `IndexUserNotificationController` (responsabilidad única: listar notificaciones del usuario)
- Crear `MarkNotificationAsReadController` (responsabilidad única: marcar notificación como leída)
- Crear `MarkAllNotificationsAsReadController` (responsabilidad única: marcar todas como leídas)
- Crear `CountUnreadNotificationsController` (responsabilidad única: contar notificaciones no leídas)

###### Sistema de Eventos y Listeners
- **Eventos:**
 - Crear `TaskAssignedEvent` (se dispara cuando se asigna una tarea)
 - Crear `CommentCreatedEvent` (se dispara cuando se crea un comentario)
 - Crear `TaskDueDateApproachingEvent` (se dispara cuando una tarea está próxima a vencer)
 - Crear `TaskStatusChangedEvent` (se dispara cuando cambia el estado de una tarea)
 - Crear `UserMentionedEvent` (se dispara cuando un usuario es mencionado)
 - Crear `AttachmentUploadedEvent` (se dispara cuando se sube un archivo)
 - Crear `ProjectStatusChangedEvent` (se dispara cuando cambia el estado de un proyecto)
 - Crear `DayEndedEvent` (se dispara al final del día laboral)
- **Listeners:**
 - Crear `TaskAssignedNotificationListener` (escucha `TaskAssignedEvent`)
 - Crear `CommentCreatedNotificationListener` (escucha `CommentCreatedEvent`)
 - Crear `TaskDueDateNotificationListener` (escucha `TaskDueDateApproachingEvent`)
 - Crear `TaskStatusChangedNotificationListener` (escucha `TaskStatusChangedEvent`)
 - Crear `UserMentionedNotificationListener` (escucha `UserMentionedEvent`)
 - Crear `AttachmentUploadedNotificationListener` (escucha `AttachmentUploadedEvent`)
 - Crear `ProjectStatusChangedNotificationListener` (escucha `ProjectStatusChangedEvent`)
 - Crear `TimeEntryReminderNotificationListener` (escucha `DayEndedEvent`)

###### Jobs programados
- Crear `CheckTasksDueDateJob` (verifica tareas próximas a vencer y dispara eventos)
- Crear `CheckTimeEntriesJob` (verifica registros de tiempo al final del día y dispara eventos)

###### Testing Backend
- Crear test para eventos y listeners
- Crear test para controladores de notificaciones
- Crear test para jobs programados

##### FRONTEND (Angular)
###### Servicios para Notificaciones (SRP)
- Crear `NotificationListService` (responsabilidad única: obtener notificaciones del usuario)
- Crear `MarkNotificationAsReadService` (responsabilidad única: marcar notificación como leída)
- Crear `MarkAllNotificationsAsReadService` (responsabilidad única: marcar todas como leídas)
- Crear `CountUnreadNotificationsService` (responsabilidad única: contar notificaciones no leídas)

###### Componentes
- Crear `NotificationIconComponent` (mostrar icono con contador de notificaciones en la barra de navegación)
- Crear `NotificationListComponent` (mostrar lista de notificaciones)
- Crear `NotificationItemComponent` (representar cada notificación individual)

- Integrar `NotificationIcon` en NavBar

##### Implementación de Eventos y Listeners

###### `TaskAssignedEvent` y `TaskAssignedNotificationListener`
- **Evento**
 - Se dispara desde `StoreTaskController` o `UpdateTaskController` cuando se asigna una tarea
 - Contiene: ID de la tarea, ID del usuario asignado, título de la tarea, ID del proyecto, nombre del proyecto
- **Listener**
 - Crea una notificación para el usuario asignado
 - Título: “Nueva tarea asignada”
 - Contenido: “Se te ha asignado la tarea ‘[título de la tarea]’ en el proyecto ‘[nombre del proyecto]’”

###### `CommentCreatedEvent` y `CommentCreatedNotificationListener`
- **Evento**
 - Se dispara desde `StoreCommentController` cuando se crea un comentario
 - Contiene: ID del comentario, ID de la tarea, ID del usuario que comenta, nombre del usuario, contenido del comentario, título de la tarea, ID del usuario asignado a la tarea
- **Listener**
 - Crea una notificación para el usuario asignado a la tarea
 - Título: “Nuevo comentario en tu tarea”
 - Contenido: “[nombre del usuario] ha comentado en la tarea ‘[título de la tarea]’: ‘[primeras 50 caracteres del comentario]…’”

###### `TaskDueDateApproachingEvent` y `TaskDueDateNotificationListener`
- **Evento**
 - Se dispara desde `CheckTasksDueDateJob` cuando una tarea está a 24 horas de vencer
 - Contiene: ID de la tarea, ID del usuario asignado, título de la tarea, fecha de vencimiento
- **Listener**
 - Crea una notificación para el usuario asignado
 - Título: “Tarea próxima a vencer”
 - Contenido: “La tarea ‘[título de la tarea]’ vence mañana”

###### `TaskStatusChangedEvent` y `TaskStatusChangedNotificationListener`
- **Evento**
 - Se dispara desde `UpdateTaskController` cuando cambia el estado de una tarea
 - Contiene: ID de la tarea, título de la tarea, estado anterior, nuevo estado, ID del creador, ID del usuario asignado
- **Listener**
 - Crea una notificación para el creador de la tarea (si es distinto del asignado)
 - Título: “Cambio de estado en tarea”
 - Contenido: “La tarea ‘[título de la tarea]’ ha cambiado a ‘[nuevo estado]’”

###### `UserMentionedEvent` y `UserMentionedNotificationListener`
- **Evento**
 - Se dispara desde `StoreCommentController` cuando se detecta una mención (@usuario)
 - Contiene: ID del comentario, ID de la tarea, título de la tarea, ID del usuario mencionado, ID del usuario que comenta, nombre del usuario que comenta, contenido del comentario
- **Listener**
 - Crea una notificación para el usuario mencionado
 - Título: “Te han mencionado en un comentario”
 - Contenido: “[nombre del usuario] te ha mencionado en un comentario: ‘[primeras 50 caracteres del comentario]…’”

###### `AttachmentUploadedEvent` y `AttachmentUploadedNotificationListener`
- **Evento**
 - Se dispara desde `StoreAttachmentController` cuando se sube un archivo
 - Contiene: ID del adjunto, nombre del archivo, ID de la tarea, título de la tarea, ID del usuario que sube, nombre del usuario, ID del usuario asignado a la tarea
- **Listener**
 - Crea una notificación para el usuario asignado a la tarea
 - Título: “Nuevo archivo adjunto”
 - Contenido: “[nombre del usuario] ha subido el archivo ‘[nombre del archivo]’ a la tarea ‘[título de la tarea]’”

###### `ProjectStatusChangedEvent` y `ProjectStatusChangedNotificationListener`
- **Evento**
 - Se dispara desde `UpdateProjectController` cuando cambia el estado de un proyecto
 - Contiene: ID del proyecto, nombre del proyecto, estado anterior, nuevo estado, lista de IDs de usuarios asignados al proyecto
- **Listener**
 - Crea notificaciones para todos los usuarios asignados al proyecto
 - Título: “Actualización de proyecto”
 - Contenido: “El proyecto ‘[nombre del proyecto]’ ha cambiado a estado ‘[nuevo estado]’”

###### `DayEndedEvent` y `TimeEntryReminderNotificationListener`
- **Evento**
 - Se dispara desde `CheckTimeEntriesJob` al final del día laboral
 - Contiene: Fecha, lista de IDs de usuarios sin registros de tiempo ese día
- **Listener**
 - Crea notificaciones para los usuarios sin registros de tiempo
 - Título: “Recordatorio de registro de tiempo”
 - Contenido: “No has registrado tiempo de trabajo hoy. Por favor, actualiza tus registros de tiempo.”

#### Ventajas de Implementar Notificaciones con Eventos
- **Desacoplamiento:** Los controladores no necesitan conocer la lógica de notificaciones, solo disparan eventos
- **Extensibilidad:** Se pueden añadir nuevos listeners sin modificar el código existente
- **Mantenibilidad:** Cada listener tiene una única responsabilidad, facilitando cambios
- **Testabilidad:** Los eventos y listeners pueden probarse de forma aislada
- **Escalabilidad:** Permite implementar fácilmente funcionalidades como notificaciones por email o push

Esta arquitectura basada en eventos es más robusta y sigue mejor los principios SOLID, especialmente el Principio de Responsabilidad Única (SRP) y el Principio Abierto/Cerrado (OCP).

---

## Enlaces de Documentación para el Sistema de Notificaciones

Para que el estudiante pueda entender e implementar correctamente el sistema de notificaciones basado en eventos, aquí tienes los recursos de documentación más relevantes que debería leer:

### Laravel - Documentación Oficial

- **Sistema de Eventos en Laravel**
  [https://laravel.com/docs/11.x/events](https://laravel.com/docs/11.x/events)
  Explica la arquitectura de eventos y listeners, cómo registrarlos y usarlos

- **Cola de Trabajos (Jobs) en Laravel**
  [https://laravel.com/docs/11.x/queues](https://laravel.com/docs/11.x/queues)
  Para implementar los jobs programados como `CheckTasksDueDateJob`

- **Programación de Tareas en Laravel**
  [https://laravel.com/docs/11.x/scheduling](https://laravel.com/docs/11.x/scheduling)
  Para programar los jobs que verifican tareas pendientes o fin del día laboral