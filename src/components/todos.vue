<template>
  <section class="todoapp">
    <header class="header">
      <h1>TodoList</h1>
      <input type="text" name="new-todo" placeholder="Ajouter une tache" v-model="newTodo" @keyup.enter="addTodo">
    </header>
    <div class="main">
      <ul class="todo-list">
        <li class="todo" v-for="todo in todos" :key="todo.name" :class="{completed: todo.completed}">
          <div class="view">
            <input type="checkbox" v-model="todo.completed" class="toggle">
            <label>{{ todo.name }}</label>
          </div>
        </li>
      </ul>
    </div>
    <footer class="footer">
      span
    </footer>
  </section>
</template>

<script>
  export default{
    data(){
      return {
        todos: [{
          name: 'tache de test',
          completed: false,
        }],
        newTodo:'',
      }
    },
    methods:{
      addTodo(){
        this.todos.push({
          completed: false,
          name: this.newTodo,
        })
        this.newTodo = ''
      }
    }
  }
</script>

<style src="./todos.css"></style>
