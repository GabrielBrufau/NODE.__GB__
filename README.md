# Node.js.__GB__
# variables de entorno en linux
```javascript
console.log(process.env.NOMBRE_DE_LA_VARIABLE_DE_ENTORNO)
```
en consola linux o mac crear una variable de entorno
```bash
export NOMBRE_DE_LA_VARIABLE_DE_ENTORNO='nombre'
```
en consola windows crear una variable de entorno
```bash
set NOMBRE_DE_LA_VARIABLE_DE_ENTORNO='nombre'
```
# manejo de errores
```javascript

callback >> function(err,data)
promesas >> .catch
async/await >> try catch

npm install --save-dev chalk
const chalk = require('chalk');
console.log(chalk.black.bgRed.bold('throw err app.js-line7 path / url does not exist'),req.url);
```

# Entrada al sistema
```bash
login:kfjasdh
password:


```
<h5>el objeto global que remplaza a window en node se llama global</h5>


# * Globales
### ?
```bash
"la ruta contenedora del archivo"
    __dirname
"la ruta completa"
    __filename
```
### funciones globales
```javascript
    
    console.time() //? corre un contador para saber que tan lento es tu codigo como parametro recibe un str
    console.endTime() //?para finalizar el contador recibe como parametro el mismo str
    console.group()
    console.warn()
    console.error()
    console.endGroup()
    console.log()
    console.table({a:a,b:b})
    setTimeout()
    clearTimeout()
    setInterval()
    clearInterval()
    
```

## levantando API falsa en localhost

 inicia un package.json que nos deja configurar el proyecto
            
            npm init -y 
            npm init --yes

 trae las dependencias para el server
          
            npm i json-server
 lo mismo pero de forma global
  
            npm install -g json-server

Create a db.json file with some data

        {"posts": [{ "id": 1, "title": "json-server", "author": "typicode" }],"comments": [ { "id": 1, "body": "some comment", "postId": 1 }],"profile":               {"name":"typicode" }}

en package.json en el "scripts"
pon 

         "server":"json-server --watch db.json"

         
para correr en puerto 4000

```bash
  "server": "json-server --watch db.json --port 4000"
```
corre el localhost/

          npm run server

Now if you go to http://localhost:3000/posts/1, you'll get THE TODO

# promesas
### las promesas bienen a solucionar el tema del dificil mantenimiento en las funciones con callback al hacerce muy grandes
### Estados de las promesas
```javascript
    fullfilled - la accion relacionada con la promesa se llevo a cabo con exito
    rejectetd - la accion relacionada con la promesa fallo
    pendind - Aun no se a determinado si la promesa fue fullfilled o rejected
    setteld - ya se ha determinado si la promesa fue fullfilled o rejected
    
    const mensaje = new Promise((resolve,reject)=>{
            setTimeout(()=>{
                if(true)
                    resolve('esto se va ejecutar')
                else
                    reject('hubo un error')
            },3000);
     });
     
     mensaje
            .then(msj=>{
                        console.log(msj);
             })
             .catch(error=>{
                        console.log(error);
             })
    
```
# async await
### llamadas asincronas
```javascript
    function mensaje(){
            return new Promise((resolve,reject)=>{
                setTimeout(()=>{
                    if(true)
                        resolve('Esto se va a ejecutar despues de 3 segunds')
                    else
                        reject('hubo un error')
                },3000);
            })
     }
     async function llamadaAsync(){
            console.log('llamada...');
            const resultado = await mensaje();
            return resultado;
     }
     llamadaAsync().then(x => console.log(x)).catch(e=> console.log(e));
```
