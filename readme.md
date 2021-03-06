# Node API

![version](https://img.shields.io/badge/javascript-Node-green.svg?maxAge=2592000)

Second hand API. Testing purpose

## Quick Start
```
docker-compose up
```


## Populate

Para cargar los datos de los anuncios y usuario podemos ejecutar el script 

```
npm run installDB
```


## Request example 

**GET**

localhost:3000/apiv1/anuncios

Usuario prueba ya creado (puedes crear tu propio usuario) 
Tomas / 1234

- Create user

**POST**

localhost:3000/apiv1/usuarios

_Body params_

nombre: [no duplicated]

clave: [pass]

email: [valid email]



## Data base connection

```
/lib/connectMongoose.js
```

```"use strict";
const mongoose = require('mongoose');
const conn = mongoose.connection;
const dbUri = 'mongodb://[ip/domain:port]/nodepopdb';
```



## Register

**POST**
nombre: [name]
clave: [pass]
email: [email valido]

### Errors

Usuario no puede estar vacio 

Usuario no puede estar duplicado

Mail con formato valido

*Estos errores no están personalizados*

*Ejemplo*
```
http://localhost:3000/apiv1/usuarios
```

*Especificar parámetros en el body*
*x-www-form-urlencoded*

## Devolver todos los tags disponibles en anuncios
```
http://localhost:3000/apiv1/anuncios/tagslista
```

## Advertisment request

GET:


```
http://localhost:3000/apiv1/anuncios
```

*Filtros*

 * tag: Devuelve todos los anuncios que contienen un determinado tag, ejemplo

```
http://localhost:3000/apiv1/anuncios?tag=mobile
```

 * venta: Anuncios que está en venta, valor *true* o *false* si se buscan, ejemplo
```
http://localhost:3000/apiv1/anuncios?venta=true
```

* precio: 10-50 , 10-, -50, 50. Precio entre 10 y 50 incluido, mayor que 10 no incluido, menor que 50 no incluido, igual a 50 respectivamente. Ejemplo:

```
http://localhost:3000/apiv1/anuncios?precio=10-50
```

*Errores Génericos*

NOT_FOUND -  404

SERVER_ERROR - 500





