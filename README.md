# node
Este tutorial node.js recoge toda la información relevante para el desarrollo en este entorno de desarrollo.

# Instalacion
El entorno de node permite ejecutar/interpretar codigo js (javascript) en un equipo, para lo cual se necesita a) instalar un editor b) instalar el runtime node.js.

## Instalacion editor
El editor se utiliza para escribir el codigo js. Con un simple editor de texto es suficiente. Cada sgit istema operativo tiene distintos editores, y ultimamente hay una serie de editores multiplataforma recomendados para programadores por incluir herramientas muy potentes y productivas como las siguientes:

[VisualStudioCode](https://code.visualstudio.com/) es un editor opensource liberado por Microsoft muy utilizado

[Atom](https://atom.io/) es un editor opensource algo menos utilizado

Los ficheros creados con estos editores contienen el codigo fuente del programa, y son ficheros con extension js 
El ciclo de trabajo es editar el fichero, salvarlo en un fichero y finalmente ejecutarlo con el runtime.

## Instalacion runtime node.js

Los ficheros de codigo fuente es simplemente javascript. El runtime node.js interprete y ejecuta tus ficheros js.
Node.js se distribuye como ficheros binarios para instalar en distintos sistemas operativos (Windows, Linux, Mac). 

Descargar la última version del binario para cada sistema operativo desde [Node.js downloads](nodejs.org/download/)

### Instalacion Windows
Usar el fichero instalador msi y seguir las instrucciones del propio instalador para instalar node.js. Por defecto el instalador instala node en el directorio C:\Program Files\nodejs. El instalador actualiza PATH del entorno con directorio C:\Program Files\nodejs\bin. Inicializar línea de comandos abierta para reflejar los cambios.

### Instalacion Unix/Linux/Mac
Descargar el fichero basado en tu arquitectura, extraerlo en un directorio temporal, y finalmente moverlo al directorio /usr/local/nodejs, con los siguientes comandos:

```
$ cd /tmp
$ wget http://nodejs.org/dist/v6.3.1/node-v6.3.1-linux-x64.tar.gz
$ tar xvfz node-v6.3.1-linux-x64.tar.gz
$ mkdir -p /usr/local/nodejs
$ mv node-v6.3.1-linux-x64/* /usr/local/nodejs
```
Finalmente actualizar el path para acceder a node de forma global:

`export PATH=$PATH:/usr/local/nodejs/bin`

### Instalacion Mac

La instalación en Mac de node y npm se recomienda seguir la instalación desde su [web](https://nodejs.org/es/download/), o como [recomendamos](https://medium.com/javascript-comunidad/c%C3%B3mo-instalar-node-js-y-npm-en-mac-9d80f26fb88d) con Homebrew mediante los siguientes pasos:

Instalar Homebrew con el siguiente comando en la terminal:

`/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

Homebrew es un gestor de paquetes para Mac al estilo de apt-get en Linux. Para instalar node usar los comandos:

```
brew install node    // Instalar node escribiendo en terminal
node -v              // comprobar version node instalada
npm -v               // comprobar version npm instalada

brew update          // Actualizar Homebrew a la ultima version
brew upgrade node    // Actualizar node
brew uninstall node  // Desinstalar node
```
### Verificar instalacion ejecutando HelloWorld.js
Crear fichero hello.js con el siguiente codigo:
```
$ echo 'console.log("Hello, World!");' > hello.js
```
o editar fichero con un editor con el siguiente codigo:
```
console.log("Hello, World!")
```
finalmente ejecutar el fichero con el siguiente comando:
```
$ node hello.js
Hello, World!
```
# Tutorial

## 01-HelloWorld

Crear fichero hello.js con editor o con el siguiente codigo:

```
$ echo 'console.log("Hello, World!");' > hello.js
$ node hello.js
Hello, World!
```

## 02-HelloServer

Crea un fichero HelloServer.js con el siguiente codigo:
```javascript
var http = require('http');

http.createServer(function (request, response) {
    response.writeHead(200, {'Content-Type': 'text/plain'});
    response.end('Hello Server\n');
}).listen(8080);

console.log('Server started');
```
Salva el fichero y ejecuta el comando:

`$ node HelloServer.js`

Verás en el terminal 'Server Started' y abriendo en navegador [http://localhost:8080](http://localhost:8080) aparece el mensaje 'Hello Server'

## 03-Counter
Presentar un contador de accesos facilmente sin necesitar ninguna base de datos creando el fichero '03-Counter.js' con el codigo:

```
var http = require('http');

var userCount = 0;
http.createServer(function (request, response) {
    console.log('New connection');
    userCount++;

    response.writeHead(200, {'Content-Type': 'text/plain'});
    response.write('Hello!\n');
    response.write('We have had '+userCount+' visits!\n');
    response.end();
}).listen(8080);

console.log('Server started');
```

ejecutar el siguiente comando,

`node 03-Counter.js`

Cuando accedemos a (http://localhost:8080) veremos un contador de vistas. El contador aumenta de dos en dos, porque en cada peticion del navegador, también se pide el favicon desde el servidor (http://localhost:8080/favicon.ico). Igualmente el servidor presenta en pantalla dos mensajes por cada petición del navegador.

## 04 - [Callbacks](http://www.theprojectspot.com/tutorial-post/nodejs-for-beginners-callbacks/4)

Now we're going to take a look at callbacks and what makes them so useful.

[Write Your Own Node.js Promise Library from Scratch](http://thecodebarbarian.com/write-your-own-node-js-promise-library-from-scratch.html)

## 05 - [server_http](https://www.nodebeginner.org/index-es.html)

# TODO
[Structuring JavaScript projects for testability](Structuring JavaScript projects for testability)
[Is async / await useless?](https://www.youtube.com/watch?v=ho5PnBOoacw)
[10 Tips for Javascript Debugging Like a PRO with Console](https://medium.com/appsflyer/10-tips-for-javascript-debugging-like-a-pro-with-console-7140027eb5f6)

[Iniciación a NodeJS con ejemplos básicos](https://github.com/LuisJoseSanchez/nodejs-iniciacion/blob/master/README.md)
[NodeJS, Express y Jade (Pug). Ejemplos básicos.](https://github.com/LuisJoseSanchez/nodejs-express-jade/blob/master/README.md)
[Aplicaciones de alto rendimiento con Node.js (V). Ejemplos de conexion a BBDD
](https://www.sidertia.com/Home/Community/Blog/2015/04/27/Aplicaciones-de-alto-rendimiento-con-Nodejs-V-Ejemplos-de-conexion-a-BBDD)

[Express.js Tutorial: Building RESTful APIs with Node and Express](https://www.youtube.com/watch?v=pKd0Rpw7O48)
[MONTAR UN API REST CON NODEJS Y EXPRESS](https://www.luisllamas.es/montar-un-api-rest-con-nodejs-y-express/)
[Como crear una API REST usando node express mongoDB](https://carlosazaustre.es/como-crear-una-api-rest-usando-node-js/)
[Iniciación a NodeJS con ejemplos básicos](https://github.com/LuisJoseSanchez/nodejs-iniciacion/blob/master/README.md)
[JavaScript in Half an Hour (Without jQuery!)](https://www.youtube.com/watch?v=zPHerhks2Vg) una demo muy basica y dinamica de como funciona javascript en browser.
[Live Coding a Trello Clone with AngularJS and Node.js (MEAN stack)](https://www.youtube.com/watch?v=ssXqKDS2dlw)


# Herramientas
[Flutter](https://flutter.io)
[How to Use npm as a Build Tool](https://www.keithcirkel.co.uk/how-to-use-npm-as-a-build-tool/)
[NPM scripts como task runner](https://blog.builtbyedgar.com/npm-scripts-como-task-runner/)

[You do console.log in any place of the code WITHOUT code modification](https://twitter.com/lavrton/status/979649815356166144?refsrc)
With @ChromeDevTools you can create "conditional breakpoint". If you add console.log into the condition, the debugger will not pause, because console.log returns undefined.

[Local Servers with public URLs]
* https://ngrok.com/
* https://serveo.net/

[Everyone can now run JavaScript on Cloudflare with Workers](https://blog.cloudflare.com/cloudflare-workers-unleashed/)

# Referencias
[Guía Estilo Google para js](https://medium.freecodecamp.org/google-publishes-a-javascript-style-guide-here-are-some-key-lessons-1810b8ad050b)
[Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

[Node.js for beginners](http://www.theprojectspot.com/tutorial-post/Node-js-for-beginners-part-1-hello-world/2)

[El libro para principiantes en node.js](https://www.nodebeginner.org/index-es.html)

[Digital Transformation with the Node.js DevOps Stack](https://github.com/jjfalcon/node/blob/master/node-js-devops-stack-transformation.pdf), PayPal, Netflix, and Walmart show the way to do rapid digital transformation of legacy systems

[How Fintonic uses Node.js, MongoDB & Kubernetes to scale](https://community.risingstack.com/how-fintonic-uses-nodejs-mongodb-kubernetes/), es un artículo sobre la arquitectura y escalabilidad de Fintonic.

# Recomendaciones

[How to prevent your Node.js process from crashing](https://medium.com/dailyjs/how-to-prevent-your-node-js-process-from-crashing-5d40247b8ab2). Una promesa sin manejar actualmente provoca un mensaje de aviso, pero en el futuro avisa que provocara el cierre del proceso node con un codigo de salida de error. Este artículo indica como reaccionar por programa a esas promesas sin manejar, por ejemplo enviando la pila de traza a uns servicio de reporting con el objetivo de tener la información y mantener el proceso activo.

# Videos/Charlas

[Hacking de Videojuegos con JavaScript](https://www.youtube.com/watch?v=XJJS1HrV2_Y) Recomendada por Bonilla

# Ejemplos
[Awesome Node.js opensource projects](https://github.com/sqreen/awesome-nodejs-projects)

[Crear una BlockChain en Node.js](https://developers.caffeina.com/chiccocoin-learn-what-is-a-blockchain-by-creating-one-in-nodejs-12929a89208b) sirve para aprender que es una Blockchain, creando una simplificacion con Node.js

[Winamp2-js](http://www.microsiervos.com/archivo/musica/winamp-html5-javascript-codigo-abierto.html) El clásico Winamp 2.9 en HTML5 y JavaScript como código abierto.

[Build a complete mobile app with Ionic 3](https://medium.com/learn-ionic-framework/build-a-complete-mobile-app-with-ionic-3-b69a8bfb0d88)
For this ionic tutorial I built an app with a question and answer format, where users will be able to ask and answer questions. The home page will have a list of categories. Each category will have a list of questions, and each question will have a list of answers. Users will also have the possibility to vote the questions and answers, plus a form for creating questions and answers.

[Friendly Pix](https://github.com/firebase/friendlypix) es un clon de Instagram desarrollado por Google como aplicacion de ejemplo usando Firebase.

[How to Create a Slack App in 3 Minutes](https://x-team.com/blog/create-slack-app-in-3-minutes/)

[A Slack app step by step](https://x-team.com/blog/slack-app-step-by-step/)

[Los 10 mejores ejemplos de aplicaciones Node.js para empresas](http://inubo.es/noticia/los-10-mejores-ejemplos-de-aplicaciones-node-js-para-empresas)

[¿Por qué usar Javascript para el IoT?](http://inubo.es/noticia/por-que-usar-javascript-para-el-iot)

[¿Por qué deberías convertir tu Mobile Site en una aplicación web progresiva (PWA)?](http://inubo.es/noticia/por-que-deberias-convertir-tu-mobile-site-en-una-aplicacion-web-progresiva-pwa)

[Los 10 mejores ejemplos de aplicaciones Node.js para empresas](http://inubo.es/noticia/los-10-mejores-ejemplos-de-aplicaciones-node-js-para-empresas)

[Calculadoras online](https://hipertextual.com/2018/03/calculadoras-online/amp)

