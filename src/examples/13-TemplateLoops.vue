<template>
  <div class="container">
    <h2>To-do List</h2>
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ index + 1 }}. {{ todo }}
      </li>
    </ul>
    <div class="form">
    <form @submit.prevent="addTodo">
      <label for="newTodo">New Task:</label>
      <input type="text" id="newTodo" v-model="newTodo">
      <button type="submit">Add</button>
    </form>
  </div>
</div>
</template>

<script>
export default {
  data() {
    return {
      todos: ['Study', 'Go to the supermarket', 'Finish the evaluation'],
      newTodo: ''
    }
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim() !== '') {
        this.todos.push(this.newTodo.trim());
        this.newTodo = ''; 
      }
    }
  }
}
</script>

<style scoped>

h2{
  font-size: 45px;
  padding-bottom: 15px
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

ul {
  list-style-type: none;
}

li {
  padding-top: 10px;
}

.form {
  text-align: center;
  padding-top: 20px;
}

</style>