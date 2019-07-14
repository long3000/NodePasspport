
## Node.JS - Login Page with MongoDB

npm i express bcryptjs passport passport-local express-ejs-layouts mongoose connect-flash express-session  
npm i -D nodemon

Tweak ``package.json`` to the following
```
  "main": "app.js",
  "scripts": {
    "start": "node app.js",
    "dev": "nodemon app.js"
  },
```

create file **app.js** and put in boilerplate code as following:
```javascript
const express = require('express');
const app = express();
const PORT = process.env.PORT || 5000;

app.listen(PORT, console.log(`Server started on port ${PORT}`));
```

 .. and type in terminal with the output expected as
 ```
 $ npm run dev
    [nodemon] 1.19.1
    [nodemon] to restart at any time, enter `rs`
    [nodemon] watching: *.*
    [nodemon] starting `node app.js`
    Server started on port 5000
 ```

 ### Files and Folders structure
 ```
 # NodeJS_Passport
 ## routes
 ### index.js
 ### users.js
 ## views
 ### welcome.ejs
 ### dashboard.ejs
 ### layout.ejs
 ### login.ejs
 ### register.ejs
 ## app.js
 ## package.json
 ```

 Install MongoDB on MacOS 
 ```
 $ brew install mongodb  
 $ sudo mkdir -p /data/db  
 $ sudo chown -R `id -un` /data/db  
 ```

 ```
 $ mongo 10.0.0.25:27017
 > use nodeauth
 > db.createCollection('users');
 > db.users.insert({name: 'Nate Nguyen', email:'nate.nguyen88@gmail.com', username: 'admin', password: '1234'});
 > db.users.find().pretty()
 ```
 <img src="https://snag.gy/2A0gVi.jpg">

**TO modify any of these fields, we can do the following:**
 ```
> db.users.update({username: 'admin'}, {$set:{email:'nate@email.com'}});
 ```