# Registration_Form
Just another registration on Internet


 # Employee Registration App

This is a simple employee registration app built using Node.js, Express, and MongoDB. The app allows users to enter their personal information and register themselves as employees.

## Prerequisites

To run this app, you will need the following:

* Node.js (version 16 or higher)
* npm (version 7 or higher)
* MongoDB (version 4 or higher)

## Installation

1. Clone the repository to your local machine.

```
git clone https://github.com/username/employee-registration-app.git
```

2. Change directory to the project folder.

```
cd employee-registration-app
```

3. Install the dependencies.

```
npm install
```

4. Start the MongoDB server.

```
mongod
```

5. Create a database named `employee-registration`.

```
mongo
use employee-registration
```

6. Start the app.

```
npm start
```

## Usage

To use the app, open your browser and navigate to `localhost:3000`. You will see a form where you can enter your personal information and register yourself as an employee.

## Code Overview

The app consists of the following files:

* `app.js`: This is the main file of the app. It sets up the Express app and defines the routes.
* `model/model.js`: This file defines the schema for the employee data.
* `db/db.js`: This file establishes the connection to the MongoDB database.
* `template/views/index.hbs`: This is the Handlebars template for the home page.

### app.js

The `app.js` file is the entry point of the app. It sets up the Express app and defines the routes.

```javascript
const express = require('express');
const app = express();

let port = 3000;
const path = require('path');
const empCollection = require('./model/model');

const template_path = path.join(__dirname, '../template/views')

app.set('view engine', 'hbs');
app.set('views', template_path); 

app.use(express.urlencoded({extended: false}));

require('./db/db');

app.get('/', (req, res)=> {
    res.render('index');
})
