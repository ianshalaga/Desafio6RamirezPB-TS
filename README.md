# Desafio6RamirezPB-TS

Sexto desafío entregable del curso de Programación Backend de CoderHouse.

## Consigna

Ajustar el servidor principal para trabajar con un sistema de login.

- [x] Se deberá contar con una estructura de **router** para **sessions** en **/api/sessions/**, el cual contará con métodos para registrar a un usuario y para su respectivo **login**.

- [x] Se deberá contar además con un **router** de vistas en la ruta base **/** para llevar al formulario de **login**, de **register** y de **profile**.

- [x] El formulario de registro insertará el usuario en la base de datos. El cual deberá contar con:

  - firstName
  - lastName
  - email
  - age
  - password

- [x] Se debe contar con el formulario de **login**, el cual corroborará que el usuario exista en la base, y además genere un objeto **user** en **req.session**, indicando que puede utilizar la página.
- [x] Agregar validaciones a las rutas de vistas para que, si aún no estoy logueado, no pueda entrar a ver mi perfil, y si ya estoy logueado, no pueda volver a loguearme o registrarme.
- [x] En la vista de perfil, se deben arrojar los datos no sensibles del usuario que se haya logueado.
- [x] Una vez completado el **login**, realizar la redirección directamente a la vista de productos.
- [x] Agregar a la vista de productos un mensaje de bienvenida con los datos del usuario.
- [x] Agregar un sistema de roles, de manera que si colocamos en el login como correo **`adminCoder@coder.com`**, y la contraseña **adminCod3r123**, el usuario de la sesión además tenga un campo **admin**.
- [x] Todos los usuarios que no sean **admin** deberán contar con un rol **user**.
- [x] Implementar botón de **logout** para destruir la sesión y redirigir a la vista de **login**.

## Entrega

Enlace al repositorio de **GitHub** con el proyecto completo, sin la carpeta de **node_modules**.

## dependencies

- `npm i express`

> **Express.js** es un **framework** minimalista y flexible para **Node.js** que simplifica el desarrollo de aplicaciones web y **APIs** al proporcionar características esenciales como enrutamiento, manejo de **middleware**, integración con motores de plantillas, gestión de errores, y más. Su enfoque modular y su extensibilidad permiten a los desarrolladores construir aplicaciones de manera rápida y eficiente, adaptándose a las necesidades específicas de sus proyectos. Express.js es ampliamente utilizado en la comunidad de **Node.js** debido a su facilidad de uso y su capacidad para construir aplicaciones web escalables y robustas.

- `npm i zod`

> **Zod** es una biblioteca de validación de datos para **TypeScript** y **JavaScript**. Proporciona una forma simple y robusta de definir esquemas de datos y validarlos en tiempo de ejecución. Permite definir fácilmente la estructura y restricciones de datos, y luego utilizar esos esquemas para validar entradas de usuario, datos de **API**, y más.

- `npm i express-handlebars`

> **Handlebars** es un motor de plantillas para **JavaScript** que permite generar **HTML** de forma dinámica al combinar datos con plantillas **HTML** predefinidas. Es especialmente útil en aplicaciones web para renderizar vistas del lado del servidor con datos dinámicos.

- `npm i socket.io`

> **Socket.io** es una biblioteca de **JavaScript** que permite la comunicación bidireccional en tiempo real entre clientes web y servidores. Proporciona una abstracción sobre **WebSockets** y otros mecanismos de transporte, lo que facilita el desarrollo de aplicaciones web en tiempo real.

- `npm i mongodb`

> Controlador oficial de **MongoDB** para **Node.js**, lo que permite a las aplicaciones **Node.js** interactuar con una base de datos **MongoDB**.

- `npm i dotenv`

> **Dotenv** es una biblioteca de **Node.js** que permite cargar variables de entorno desde un archivo **.env** en tu aplicación.

- `npm i mongoose`

> **Mongoose** es una biblioteca de modelado de objetos de **MongoDB** para **Node.js**. Proporciona una solución basada en esquemas para modelar datos de aplicaciones utilizando **MongoDB**, lo que facilita la interacción con la base de datos **MongoDB** desde una aplicación **Node.js**.

- `npm i mongoose-paginate-v2`

> **mongoose-paginate-v2** proporciona funcionalidades de paginación para consultas en **MongoDB** utilizando **Mongoose**.

- `npm i cookie-parser`

> **Middleware** que facilita la manipulación de **cookies** en las aplicaciones web con **Express**.

- `npm i express-session`

> **Middleware** esencial para la gestión de sesiones en aplicaciones **Express**.

- `npm i connect-mongo`

> Es una herramienta para almacenar sesiones de usuario de forma persistente en una base de datos **MongoDB** en aplicaciones **Express.js**, proporcionando beneficios en términos de persistencia, escalabilidad y seguridad.

## devDependencies

- `npm i nodemon -D`

> **Nodemon** reinicia automáticamente el servidor en cuanto detecta que hay cambios en el código.

- `npm i typescript -D` (Compilador de **TypeScript**)
- `npm i tsx -D` (Motor de ejecución de **TypeScript** para paquetes de tipo **module**)
- `npm i @types/node -D` (Definiciones de tipos de **TypeScript** para **Node.js**)
- `npm i @types/express -D` (Definiciones de tipos de **TypeScript** para **Express.js**)
- `npm i @types/cookie-parser -D` (Definiciones de tipos de **TypeScript** para **cookie-parser**)
- `npm i @types/express-session -D` (Definiciones de tipos de **TypeScript** para **express-session**)

> **TypeScript** dependencies.

- `npm i tailwindcss -D`
- `npm i @tailwindcss/forms -D` (Conjunto de estilos predefinidos diseñados específicamente para mejorar el aspecto y la funcionalidad de los formularios **HTML**)

> Styles: **TailwindCSS**

## package.json

Se ubica en el directorio raíz.

- `"type": "module"`

> El proyecto utiliza módulos **ECMAScript** (**ESM**) en lugar de **CommonJS** para la gestión de módulos en **Node.js**. Permite utilizar la sintaxis de importación (**import**) y exportación (**export**) de **ECMAScript** estándar en lugar de la sintaxis **require** y **module.exports** de **CommonJS**.

## nodemon.json

Se ubica en el directorio raíz.

```json
{
  "watch": ["src", "public"],
  "ext": "js ts handlebars",
  "exec": "npx tailwindcss -i ./public/css/tailwind.css -o ./public/css/app.css && tsx ./src/app.ts"
}
```

> Al ejecutar con **nodemon** se compila el **css** y se ejecuta la **app**.

## tsconfig.json

Se ubica en el directorio raíz. Se especifican las opciones de configuración para el compilador de **TypeScript**.

```json
{
  "compilerOptions": {
    "esModuleInterop": true,
    "module": "ESNext",
    "moduleResolution": "Node"
  }
}
```

> - **"esModuleInterop": true**: **TypeScript** interpreta las importaciones predeterminadas (**import express from 'express'**) como si fueran importaciones de asignación (**import \* as express from 'express'**). Permite una mayor compatibilidad en las importaciones entre los diferentes estilos de exportación de módulos.
> - **"module": "ESNext"**: especifica el formato de módulo que se utilizará en la salida del compilador de **TypeScript**. **ESNext** indica que se utilizará el formato de módulo **ECMAScript** más reciente compatible con el entorno de ejecución.
> - **"moduleResolution": "Node"**: especifica el método de resolución de módulos que **TypeScript** utilizará al importar módulos. **TypeScript** utilizará la resolución de módulos de **Node.js** siguiendo la estructura de carpetas y los archivos **node_modules** para buscar y resolver las dependencias de los módulos.

## Ejecución

- **Scripts**: `tsx script.ts`.
- **TailwindCSS**: `npx tailwindcss -i tailwind.css -o output.css`
- **Nodemon**: `nodemon --exec tsx script.ts`

## JSON Formatter

- [JSON Formatter](https://chromewebstore.google.com/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa)

> Extensión para navegadores basados en Chromium.
