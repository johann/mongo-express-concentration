## Mongo & Express

Things to get done 
* Set up mongo
  - You should be able to type `mongod` and `mongo` in your terminal. To start your mongo server you must run `mongod`. `mongo` is used if you want to open the Mongo Shell. You can find some interesting commands for the shell [shell](https://docs.mongodb.com/manual/reference/mongo-shell/)
* Set up Express with React
  * Create a React app with `create-react-app`
  * Inside of that app copy the package.json into another file. You may type `mv package.json copy.json`
  * Create your express application by typing `express .`. This will generate a new Express project
  * Combine the `package.json` file with the `copy.json` file.
```
  {
  "name": "twitter",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node ./bin/www",
    "react-start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test --env=jsdom",
    "eject": "react-scripts eject"
  },
  "dependencies": {
    "body-parser": "~1.17.1",
    "cookie-parser": "~1.4.3",
    "debug": "~2.6.3",
    "express": "~4.15.2",
    "jade": "~1.11.0",
    "morgan": "~1.8.1",
    "serve-favicon": "~2.4.2",
    "react": "^16.1.0",
    "react-dom": "^16.1.0"
  },
  "devDependencies": {
    "react-scripts": "1.0.17"
  }
}


```
  * Once this is done you need to change your app.js file
    ```
    app.use(express.static(path.join(__dirname, 'build')));
    
    // app.set('views', path.join(__dirname, 'views'));
    // app.set('view engine', 'jade');
    
    
    // make this your last route. The * acts like a wildcard so it catches all routes
    app.get("*", (req, res) => {
      res.sendFile(__dirname + '/build/index.html')
    })

    
    
    ```
    
    
  * In your package.json change your start scripts. `npm run build && nodemon ./bin/www`. This will build your react project and create a `build` folder while running `node ./bin/www`
    

