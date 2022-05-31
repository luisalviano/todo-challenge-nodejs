<h1 align="center">🚀 Challenge #1 - Node.js Concepts 🚀</h1>

This is the first challenge from [Rocketseat's Ignite](https://www.rocketseat.com.br/ignite) Node.js bootcamp. The objective of this challenge is to practice the basic concepts of Node.js.

<p align="center">
  <a href="#about-the-application">About</a> •
  <a href="#technologies">Technologies</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#routes">Routes</a> •
  <a href="#running-the-tests">Tests<a>
</p>

<p id="insomnia" align="center">
  <a href="https://insomnia.rest/run/?label=ToDo%20App&uri=https%3A%2F%2Fgithub.com%2Fmarialuizams%2Ftodo-challenge-nodejs%2Fblob%2Fmain%2Finsomnia.json" target="_blank"><img src="https://insomnia.rest/images/run.svg" alt="Run in Insomnia"></a>
</p>

## About the application

This project is a simple task manager application, where it must be possible to create an user, as well as the <i>todos</i> (tasks) CRUD:

- Create a new <i>todo</i>;
- List all <i>todos</i>;
- Update `title` and `deadline` of an existing <i>todo</i>;
- Check a <i>todo</i> as done;
- Delete a <i>todo</i>.

## Technologies

- [Node.js](https://nodejs.org/en/)
- [Express](http://expressjs.com/)
- [Jest](https://jestjs.io/)

## Getting Started

Clone this repository and access the folder:
```
$ git clone https://github.com/marialuizams/todo-challenge-nodejs
$ cd todo-challenge-nodejs
```
Install dependencies using:
```
$ yarn
# or
$ npm install
```

Start the app by running:
```
$ yarn dev
```
The application should start running on http://localhost:3333.

Import the `insomnia.json` file on the Insomnia app, or click the [Run in Insomnia](#insomnia) button.

## Routes

### POST `/users`

This route should receive the user's `name` and `username` via request body:

```json
{
  "name": "John Doe",
  "username": "john"
}
```
The user must be stored in an object and returned as the method's response:

```json
{
  "id": "uuid", // the id MUST be an uuid value
  "name": "John Doe",
  "username": "john",
  "todos": [] // todos MUST be initialized as an empty array
}
```
### GET `/todos`

This route should receive the `username` via header and return a list containing the user's <i>todos</i>.

### POST `/todos`

This route should receive `title` and `deadline` inside the request body, and the user's `username` via header.

```json
{
  "title": "ToDo #1",
  "deadline": "2022-02-27"
}
```
Once a new <i>todo</i> is created, it should be stored inside the `todo` list of the user that is creating this task. Each task should be stored in an object and returned as the method's response.
```json
{
  "id": "uuid",
  "title": "ToDo #1",
  "done": false, 
  "deadline": "2022-02-27T00:00:00.000Z", 
  "created_at": "2022-02-22T00:00:00.000Z"
}
```
The property `done` must be initialized as `false` when a new task is created.

### PUT `/todos/:id`

This route should receive the `username` through the request's header, and the `title` and `deadline` via body. Only the `title` and `deadline` of the task in which the `id` is equal to the `id` received in the route parameters will be updated. The method will return the `todo` object with the updated properties.

### PATCH `/todos/:id/done`

This route should receive the `username` through the request's header and change to `true` the `done` property of the task that has an `id` equal to the `id` received in the route parameters. 

### DELETE `/todos/:id`

This route should receive the `username` through the request's reader and delete the task in which the `id` is equal to the `id` received in the route parameters.

## Running the tests
To run the tests using Jest:
```
$ yarn test
```

![Jest output](/assets/test_evidence.png)

#

<p align="center">Developed by <a href="https://www.linkedin.com/in/marialuizasalviano/">Maria Luiza Salviano</a></p>