# GlowCare

Tienda virtual de productos para el cuidado de la piel.

## Objetivo

Facilitar la búsqueda y compra de productos para el cuidado de la piel mediante una plataforma organizada, con información clara y opciones que respondan a las necesidades de los usuarios.

## Problema que resuelve

Muchas personas tienen dificultades para identificar productos adecuados para su tipo de piel cuando compran por Internet. La información incompleta y la falta de opiniones también pueden generar dudas durante la compra.

GlowCare propone reunir un catálogo organizado, información detallada, filtros y opiniones de compradores para facilitar la elección de productos.

## Funcionalidades principales previstas

- Registro e inicio de sesión de usuarios.
- Consulta del catálogo organizado por categorías.
- Búsqueda de productos por nombre.
- Filtrado según el tipo o la necesidad de piel.
- Consulta de ingredientes, beneficios, forma de uso y características de los productos.
- Consulta de opiniones y calificaciones.
- Gestión del carrito de compras.
- Selección de pago con tarjeta o contra entrega.
- Validación del pago y confirmación de la compra.
- Seguimiento de pedidos.

Estas funcionalidades forman parte del alcance propuesto y todavía requieren implementación y pruebas.

## Arquitectura seleccionada

Se seleccionó una arquitectura por capas con separación entre frontend y backend, aplicando el principio de separación de responsabilidades.

- Presentación: interfaz con la que interactúa el usuario.
- Lógica de negocio: reglas y operaciones del sistema, autenticación y coordinación del proceso de compra.
- Acceso a datos y persistencia: consulta y almacenamiento de la información.
- Servicio externo de pago: procesamiento o validación de las transacciones con tarjeta.

La arquitectura inicial está documentada en la actividad de la Semana V y vinculada al Issue #13.


## Organización propuesta del frontend y backend

### Frontend

Sería la parte visible de GlowCare. Presentaría las pantallas de registro, inicio de sesión, catálogo, detalles del producto, opiniones, carrito y selección del método de pago.

Su responsabilidad sería recibir las acciones del usuario, enviar solicitudes al backend y mostrar los resultados, las confirmaciones y los mensajes de error.

El código de esta parte se organizaría en una carpeta `frontend`, con las pantallas, componentes visuales, estilos y funciones de comunicación con el backend.


### Backend

Se encargaría de procesar las solicitudes, validar los datos y aplicar las reglas del sistema. Gestionaría la autenticación, las consultas de productos, las opiniones, el carrito, los pedidos y los pagos.

También controlaría el acceso a la base de datos y la comunicación con el servicio de pago externo. La interfaz no accedería directamente a la base de datos.

El código se organizaría en una carpeta `backend`, con rutas de la API, servicios de negocio, validaciones y acceso a datos.


### Comunicación entre ambas partes

Se propone que frontend y backend se comuniquen mediante una API utilizando solicitudes HTTPS y respuestas en formato JSON.

Por ejemplo, cuando el cliente aplique un filtro, el frontend enviaría la selección al backend. Este consultaría los productos correspondientes y devolvería los resultados para mostrarlos en el catálogo.

Durante un pago con tarjeta, el backend coordinaría la solicitud al servicio de pago externo y registraría el resultado. Para el pago contra entrega, registraría el método elegido y el pedido sin realizar un cobro con tarjeta.

Esta organización es una propuesta de diseño, las carpetas de código y la API todavía no están implementadas.

## Herramientas utilizadas

- GitHub: repositorio y registro de cambios mediante commits.
- GitHub Issues: seguimiento de requisitos y tareas técnicas.
- GitHub Projects: organización del trabajo en un tablero Kanban.
- Visual Paradigm Online: elaboración de diagramas UML y arquitectura.
- Google Forms: encuesta para el levantamiento de requisitos.
- Word y PDF: elaboración y conservación de la documentación académica.
- Canva: preparación del mensaje de validación de arquitectura.

## Documentación técnica

Las evidencias se encuentran en la carpeta [docs](./docs):

- Semana II: planificación inicial y organización del proyecto.
- Semana III: encuesta, historias de usuario, requisitos y trazabilidad.
- Semana IV: modelado UML y validación de los diagramas.
- Semana V: arquitectura inicial y responsabilidades de los componentes.
- Semana VI: seguimiento de tareas y matriz de riesgos.
- Semana VII: comunicación con interesados y reporte técnico de avance.
- Imágenes de los diagramas de casos de uso, clases, secuencia, colaboración y actividades.
- Mensaje de solicitud de validación de la arquitectura.


## Gestión del avance

El tablero utiliza las columnas Backlog, Por hacer, En progreso, En revisión y Finalizado. Las tareas deben ubicarse según su avance real.

[Consultar el tablero de GitHub Projects](https://github.com/users/gjanielfeliz-hub/projects/1/views/1)

[Consultar los Issues del repositorio](https://github.com/gjanielfeliz-hub/glowcare-tienda-skin-care/issues)


## Estado actual del proyecto

GlowCare se encuentra en una etapa de planificación, análisis y diseño. Se han documentado los requisitos, la trazabilidad, los modelos UML, la arquitectura inicial, los riesgos y el seguimiento de las tareas.

El repositorio reúne una base documental del proyecto. Todavía no contiene una aplicación ejecutable ni una integración funcional con una base de datos o un servicio de pago.

Quedan pendientes la implementación de las funcionalidades, la integración entre componentes y las pruebas del sistema.


## Próximo paso técnico

Revisar la coherencia entre requisitos, modelos y arquitectura, completar el diseño de las interfaces y del esquema de base de datos, y preparar el plan de pruebas antes de avanzar con la implementación.
