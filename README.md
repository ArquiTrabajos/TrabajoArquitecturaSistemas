# ![logo-002](https://user-images.githubusercontent.com/90181028/217143286-a023dd4b-f3a7-4218-8802-39a3bd2b15a8.png)

[![RealWorld Frontend](https://img.shields.io/badge/realworld-frontend-%23783578.svg)](http://realworld.io)

> ### Código de React + React Query que contiene ejemplos del mundo real (CRUD, autenticación, patrones avanzados, etc.) que cumple con las especificaciones y API de [RealWorld](https://github.com/gothinkster/realworld).

### [Demo](https://react-query-realworld.netlify.app)&nbsp;&nbsp;&nbsp;&nbsp;[RealWorld](https://github.com/gothinkster/realworld)

Este código fue creado para demostrar una aplicación fullstack construida con **React + React Query**, incluyendo operaciones CRUD, autenticación, enrutamiento, paginación y más.

Nos hemos esforzado por seguir las mejores prácticas y guías de estilo de la comunidad [TanStack Query](https://tanstack.com/query/latest/docs/react/overview).

Para obtener más información sobre cómo funciona con otros frontends/backends, diríjase al repositorio [RealWorld](https://github.com/gothinkster/realworld).

# Cómo funciona

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


