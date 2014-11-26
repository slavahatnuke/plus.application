# application skeleton / plus.application

The main goal of this package that loading app configuration and app services.

it uses 2 packages `plus.config` and `plus.container` and helps to manage application configuration and dependency injection.
it has 2 parameters `dir` and `env` it loads form file system configuration and container (services) for some environment.



## Usage

### Dir

```

|-- config.json
|-- config_dev.json
|-- config_prod.json
|-- config_test.json
|-- container.js
|-- container_dev.js
|-- container_prod.js
`-- container_test.js

```

### App.js
```

// app.js example

    var Application = require('plus.application');

            var app = new Application({
                dir: __dirname,
                env: process.env.NODE_ENV || 'dev' // it works in the 'dev' environment by default
            });

            app.config.get('port');
            app.container.get('myService1');

            // app.config instanceof require('plus.config')
            // app.container instanceof require('plus.container')


```


// config.json example
```
{
    "port": 3000
}
```

// container.js example
```
module.exports = function (container) {

    var Class1 = function(){  }
    var Class2 = function(){ }

    container.register('myService1', Class1);
    container.register('myService2', Class2);
}
```


Please take a look on:
- `plus.config` - https://www.npmjs.org/package/plus.config
- `plus.container` - https://www.npmjs.org/package/plus.container


