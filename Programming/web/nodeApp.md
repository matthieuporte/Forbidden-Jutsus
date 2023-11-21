

# How to create a Node app.

### Initialisation of the backend

- npm init
- install all your module, use the --save-dev option if you're not using the module in prod.

often used modules : express,mongoose,cors,dotenv,lodash,express-async-errors,bcrypt,mongoose-unique-validator,jsonwebtoken
often used developpement modules : nodemon,jest,eslint,supertest

### Initialisation of the frontend

- npx create-react-app appName
- cd appName

often used modules : axios,mui,prop-types,redux,react-redux,@reduxjs/toolkit,react-query,react-router-dom
often used dev modules : eslint-plugin-jest,@testing-library/react,@testing-library/jest-dom,@testing-library/user-event,cypress,eslint-plugin-cypress,deep-freeze

### The architecture of a node app

 - **index.js** is the first script, it requires app.js and config.js to listen to the given server port.

- **app.js** is the main script. It setups the express app, connects to the database, and use the routers.

- **/utils** is where all the debug/dev scripts are going to be stored. Scripts such as middleware, loggers and the config file.

- **/test** speaks for itself

- **/model** is where the line models for mongodb are going to be stored

- **/controllers** is where the routers are going to be created, along with their routes

### package.json

here are a lot of information about your app: you can see the name, description, what are the dependencies but most importantly you can write scripts (a bit like an alias in .bashrc).

Here are some scripts that I find useful :
```json
"scripts": {
    "start": "node index.js",
    "dev": "nodemon index.js",
    "build:ui": "rm -rf build && cd ../frontend/ && npm run build && cp -r build ../backend",
    "deploy": "fly deploy",
    "deploy:full": "npm run build:ui && npm run deploy",
    "logs:prod": "fly logs",
    "lint": "eslint .",
    "lint:fix": "eslint . --fix",
    "test": "jest --verbose --runInBand"
  },
```

### eslint 

```
npx eslint --init
```


### Testing

Testing is very usefull when building apps.
I use Jest.

#### backend

to run all test (since it is defined in the package.json) I do
```
npm test
```
but if I want to run a specific suite I can do
```
npm test -- tests/blogs_api.test.js
```
and to test a specific test I do
```
npm test -- -t "name of my test"
```

In my unit test, when I do requests sometimes it's hard to console.log during a request. To do it I do : 
```
.expect(response => {console.log(response)})
```

#### frontend 
to run my test in the front end I configure my package.json as such (in scripts): 
```
"test": "react-scripts test",
"tests": "CI=true npm test",
```
then I run
```
npm run tests
```

### Redux

use redux to manage the state of your app

#### Redux-toolkit

redux toolkit is yet another powerful tool that makes the whole developpement process faster. 
to console log inside a slice you need to do :
```
console.log(JSON.parse(JSON.stringify(state)))
```

### Keeping the app up to date

you can see which dependencies are outdated by running 
```
npm outdated --depth 0
```

and then you can update your packages with 

```
npm install -g npm-check-updates
```
