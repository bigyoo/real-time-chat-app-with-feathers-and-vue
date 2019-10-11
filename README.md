# real-time-chat-app-with-feathers-and-vue

> Real time chat application with Feathers and Vue.js

## About

This project uses [Feathers](http://feathersjs.com). An open source web framework for building modern real-time applications.

## Getting Started

Getting up and running is as easy as 1, 2, 3.

1. Make sure you have [NodeJS](https://nodejs.org/) and [npm](https://www.npmjs.com/) installed.
2. Install your dependencies

    ```
    cd path/to/real-time-chat-app-with-feathers-and-vue
    npm install
    ```

3. Start your app

    ```
    npm start
    ```

## Testing

Simply run `npm test` and all your tests in the `test/` directory will be run.

## Scaffolding

Feathers has a powerful command line interface. Here are a few things it can do:

```
$ npm install -g @feathersjs/cli          # Install Feathers CLI

$ feathers generate service               # Generate a new Service
$ feathers generate hook                  # Generate a new Hook
$ feathers help                           # Show all commands
```

## Help

For more information on all the things you can do with Feathers visit [docs.feathersjs.com](http://docs.feathersjs.com).


## Hot to reproduce it from scratch

* [ ] Generate backend code with Feathers
    ```
    feather g app
    ```
* [ ] Review the generated folders
* [ ] Start MongoDB
    ```
    docker run -p 27017:27017 --name my-mongo -d mongo
    ```
* [ ] Start the application
    ```
    npm start
    ```
* [ ] Try out the REST api from Postman (get users, create user, authentication
* [ ] Create a service for the messages 
    ```
    feather g service
    ```
* [ ] Demonstrate how to create messages
* [ ] Set 'author' on new messages automatically 
    ```
    context.data.author = context.params.user.email; 
    ```
* [ ] Create client
    ```
    <script type="text/javascript" src="//cdnjs.cloudflare.com/ajax/libs/core-js/2.1.4/core.min.js"></script>
    <script src="//unpkg.com/@feathersjs/client@^3.0.0/dist/feathers.js"></script>
    <script src="//unpkg.com/socket.io-client@1.7.3/dist/socket.io.js"></script>
    ```

    ```
    // Socket.io is exposed as the `io` global.
    var socket = io('http://localhost:3030');
    // @feathersjs/client is exposed as the `feathers` global.
    var app = feathers();

    app.configure(feathers.socketio(socket));
    app.configure(feathers.authentication());

    app.service('messages').create({
        text: 'A new message'
    });
    ```
