<template>
  <div id="app">
  <!-- <header>
    <nav>
      <ul>
          <li class="nav-item">
            <img class="logo" src="./assets/build-a-bot-logo.png" alt="">
            Build A Robot
          </li>
      </ul>
    </nav>
  </header> -->
    <main>
    <!-- <HomePage/> -->
      <!-- <RobortBuilder/> -->
      <!-- <Todos/> -->
      
      <Todos v-bind:todos="todos" />
    </main>
  </div>
</template>
<script>
// import HomePage from './home/HomePage.vue'
// import RobortBuilder from './build/RobortBuilder.vue'
import Todos from './build/Todos.vue';
// import Todos from './TodoApp/Todos.vue';
export default {
  name: 'App',
  components: {
    // RobortBuilder,
    // HomePage
    Todos
    // Todos 
  },
  data() {
    return {
     todos : [
        {
          id:1,
          title:'Todos one',
          completed:false
        },
        {
          id:2,
          title:'Todos Two',
          completed:false
        },
        {
          id:3,
          title:'Todos Two',
          completed:false
        },
        
     ]
    }
  },
}
</script>

<style>
  body{
  background-attachment: fixed;
    background:linear-gradient(to bottom, #555, #999);
  }
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
  
  header {
  background-color: #999;
  width: 1084px;
  margin: 0 auto;
}
ul {
  /* display: flex; */
}
.nav-item {
  display: inline-block;
  padding: 5px 10px;
  font-size: 22px;
  border-right: 1px solid #bbb;
}
.logo {
  vertical-align: middle;
  height: 30px;
}
  
  main {
    margin:auto;
    padding: 30px;
    background: #fff;
    width:1024px;
    min-height:300px;
  }
</style>
