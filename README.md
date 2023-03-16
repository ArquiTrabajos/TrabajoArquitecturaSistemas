# ![logo-002](https://user-images.githubusercontent.com/90181028/217143286-a023dd4b-f3a7-4218-8802-39a3bd2b15a8.png)

[![RealWorld Frontend](https://img.shields.io/badge/realworld-frontend-%23783578.svg)](http://realworld.io)

> ### Código de React + React Query que contiene ejemplos del mundo real (CRUD, autenticación, patrones avanzados, etc.) que cumple con las especificaciones y API de [RealWorld](https://github.com/gothinkster/realworld).

### [Demo](https://react-query-realworld.netlify.app)&nbsp;&nbsp;&nbsp;&nbsp;[RealWorld](https://github.com/gothinkster/realworld)

Este código fue creado para demostrar una aplicación fullstack construida con **React + React Query**, incluyendo operaciones CRUD, autenticación, enrutamiento, paginación y más.

Nos hemos esforzado por seguir las mejores prácticas y guías de estilo de la comunidad [TanStack Query](https://tanstack.com/query/latest/docs/react/overview).

Para obtener más información sobre cómo funciona con otros frontends/backends, diríjase al repositorio [RealWorld](https://github.com/gothinkster/realworld).

# Esctructura

```bash
src
├─ App.tsx
├─ index.tsx
├─ react-app-env.d.ts
├─ Router.tsx # asignación dinámica de router
├─ components # componentes
├─ constants # constantes
├─ contexts # API de contexto
├─ lib
│  ├─ routerMeta.ts # meta datos del router
│  ├─ token.ts # clase de almacenamiento local
│  ├─ utils # funciones de utilidad
│  └─ hooks # hooks personalizados
├─ pages # componentes de página
├─ queries # funciones de react query
└─ repositories # servicio api
    └─ apiClient.ts # instancia y interceptor de Axios
    

 ## Demo

https://youtu.be/Iw2VxlXVcXo


# Realizando solicitudes a la API del backend

Para mayor comodidad, tenemos un servidor de API en vivo funcionando en https://conduit.productionready.io/api para que la aplicación realice solicitudes. Puede ver la especificación de la API aquí, que contiene todas las rutas y respuestas para el servidor.

El código fuente del servidor backend (disponible para Node, Rails y Django) se puede encontrar en el repositorio principal de RealWorld.

## Uso de plantillas marcadas

Puede verificar la especificación del frontend marcado aquí.

## Run Locally

Clone the project
``` bash
  git clone https://github.com/ArquiTrabajos/TrabajoArquitecturaSistemas
```
Go to the project directory
``` bash
  cd my-project
```
Install dependencies
```bash
  npm install
```
```bash
 npm run build
```
Start the server

```bash
  npm start
```

## Descripción general de la funcionalidad
  Guias para el awesome README
 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)


La aplicación de ejemplo es un sitio de blogs sociales (es decir, un clon de Medium.com) llamado "Conduit". Utiliza una API personalizada para todas las solicitudes, incluida la autenticación. Puede ver una demostración en vivo en https://react-query-realworld.netlify.app.

## Funcionalidad general:

- Autenticar usuarios mediante JWT (páginas de inicio de sesión/registro + botón de cierre de sesión en la página de configuración)
- CRUD usuarios (página de registro y configuración - no se requiere eliminación)
- CRUD Artículos
- CRUD Comentarios sobre artículos (no se requiere actualización)
- Obtener y mostrar listas paginadas de artículos
- Artículos favoritos
- Seguir a otros usuarios
- La descomposición general de la página se ve así:

## Página de inicio (URL: /#/ )
- Lista de etiquetas
- Lista de artículos extraídos de Feed, Global o por Tag
- Paginación para la lista de artículos
- Páginas de inicio de sesión/registro (URL: /#/login, /#/register )
- Utiliza JWT (almacena el token en localStorage)
- La autenticación se puede cambiar fácilmente a basada en sesión/cookie
- Página de configuración (URL: /#/settings )
- Página de editor para crear/editar artículos (URL: /#/editor, /#/editor/article-slug-here )
- Página de artículo (URL: /#/article/article-slug-here )
- Botón para eliminar artículo (solo se muestra al autor del artículo)
- Renderizar markdown del servidor en el lado del cliente
- Sección de comentarios en la parte inferior de la página
- Botón para eliminar comentario (solo se muestra al autor del comentario)
- Página de perfil (URL: /#/profile/:username, /#/profile/:username/favorites )
- Mostrar información básica del usuario
- Lista de artículos populares de los artículos creados por el -autor o de los artículos favoritos del autor

## Arquitectur Modulos

Módulo de presentación: Este módulo contendría todos los componentes y recursos necesarios para mostrar la interfaz de usuario, incluyendo las páginas, la lógica de presentación y la representación visual. Sería responsable de manejar la navegación del usuario y la interacción con el sistema.

Módulo de autenticación y autorización: Este módulo estaría encargado de manejar la seguridad del sistema, incluyendo la autenticación y autorización de usuarios. Sería responsable de generar y validar los tokens JWT, así como de verificar las credenciales de los usuarios y sus permisos de acceso.

Módulo de gestión de artículos: Este módulo se encargaría de manejar la creación, edición, eliminación y visualización de los artículos en el sistema. Contendría la lógica de negocio para la manipulación de los artículos, así como los servicios necesarios para acceder a los datos.

Módulo de gestión de etiquetas: Este módulo estaría encargado de manejar la creación, edición, eliminación y visualización de las etiquetas en el sistema. Sería responsable de mantener la integridad y consistencia de las etiquetas en los artículos.

Módulo de gestión de comentarios: Este módulo se encargaría de manejar la creación, edición, eliminación y visualización de los comentarios en el sistema. Contendría la lógica de negocio para la manipulación de los comentarios, así como los servicios necesarios para acceder a los datos.

Módulo de gestión de perfiles: Este módulo estaría encargado de manejar los perfiles de usuario, incluyendo la información básica de los usuarios, la lista de artículos creados y la lista de artículos favoritos. Sería responsable de mantener la integridad y consistencia de los perfiles de usuario en el sistema.

Módulo de persistencia de datos: Este módulo se encargaría de almacenar y acceder a los datos del sistema, incluyendo los artículos, etiquetas, comentarios y perfiles de usuario. Contendría la lógica necesaria para acceder y manipular los datos en el almacenamiento persistente.

                               +--------------------+
                          |    Módulo de        |
                          |    Presentación     |
                          +--------------------+
                                     |
                                     |
                          +--------------------+
                          | Módulo de Autentic. |
                          | y Autorización     |
                          +--------------------+
                                     |
                                     |
                +------------------------+------------------------+
                |                        |                        |
      +--------------------+  +--------------------+  +--------------------+
      | Módulo de Gestión de |  | Módulo de Gestión de |  | Módulo de Gestión de |
      |      Artículos      |  |       Etiquetas      |  |      Comentarios     |
      +--------------------+  +--------------------+  +--------------------+
                                     |
                                     |
                          +--------------------+
                          |  Módulo de Gestión  |
                          |      de Perfiles    |
                          +--------------------+
                                     |
                                     |
                          +--------------------+
                          | Módulo de Persist.   |
                          |     de Datos        |
                          +--------------------+



