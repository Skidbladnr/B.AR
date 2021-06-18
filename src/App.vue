<template>
  <div>
    
    <div style = "position:relative; left:600px; top:200px; background-color:white;">
      <form @submit.prevent="add">
        <input v-model="todo" />
        <button type="submit">Add to List</button>
      </form>
    </div>
    <div style = "position:center; left:600px; top:px;">
          <img src="@/assets/logo.png" width="150" height="150"/>
    </div>
    <div style = "font-family: Helvetica; position:relative; left:600px; top:50px;">
    
      <div v-for="(todo, index) of todos" :key="todo.id">
        {{ todo.todo }}
        <button @click="deleteTodo(index)">Remove from List</button>
      </div>
    </div>

  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content='ie=edge'
    <title>Side Menu</title>
    <link rel="stylesheet" href="/Users/taiga/node_modules/vue-router/my-project/src/SideNav.css">
  </head>
  <body>
    <nav class="sidebar">
      <span class="open-slide">
        <a href="#" onclick="openSlideMenu()">
          <svg width="30" height="30">
            <path d="M0,5 30,5" stroke="#000" stroke-width="5"/>
            <path d="M0,14 30,14" stroke="#000" stroke-width="5"/>
            <path d="M0,23 30,23" stroke="#000" stroke-width="5"/>
          </svg>
        </a>
      </span>

      <ul class="navbar-nav">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
    <div id="side-menu" class="side-nav">
      <a href="#" class="btn-close" onclick="closeSlideMenu()">&times;</a>
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Services</a>
      <a href="#">Contact</a>
    </div>
    <div id="main">
      <h1> Side Menu </h1>
    </div>
  </body>
  </div>
</template>
<script>
    import { v4 as uuidv4 } from "uuid";

    export default {
    name: "App",
    data() {
      return {
        todo: "",
        todos: [],
      };
    },
    methods: {
      add() {
        const { todo } = this;
        this.todos.push({
          id: uuidv4(),
          todo,
        });
        this.todo = "";
      },
      deleteTodo(index) {
        this.todos.splice(index, 1);
      },
    },
    };
  function openSlideMenu(){
    document.getElementByID('side-menu').style.width = '250px';
    document.getElementByID('main').style.marginLeft = '250px';
  }
</script>


