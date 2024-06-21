<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      phone: '',
      password: '',
      confirmPassword: ''
    }
  },
  methods: {
    submitForm() {
      console.log('Form Sent!');
      console.log(`Name: ${this.name}`);
      console.log(`Email: ${this.email}`);
      console.log(`Phone: ${this.phone}`);
      console.log(`Senha: ${this.password}`);
      console.log(`Confirmar Senha: ${this.confirmPassword}`);

      this.name = '';
      this.email = '';
      this.phone = '';
      this.password = '';
      this.confirmPassword = '';
    }
  }
}
</script>

<template>
    <h1>Register</h1>
    <form @submit.prevent="submitForm">
      
        <label for="nome">Name:</label>
        <input type="text" id="nome" v-model="name" placeholder="Name"/>
      
      
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" placeholder="email"/>

        <label for="phone">Telephone:</label>
        <input type="tel" id="phone" v-model="phone" placeholder="Telephone" />

        <label for="senha">password:</label>
        <input type="password" id="senha" v-model="password" placeholder="Password"/>
      
        <label for="confirmar-senha">Confirm password:</label>
        <input type="password" id="confirmPassword" v-model="confirmPassword" placeholder="Confirm password"/>
      
      <button type="submit">Register</button>

    </form>
  
</template>

<style scoped>
h1{
  font-size: 45px;
  text-align: center;
  color: black;
  font-weight: bold;
}

form {
  display: flex;
  flex-direction: column;
  align-items: center;
}

input {
  cursor: pointer;
  text-align: center;
  border: 1px solid #ccc;
  display: inline-block;
  margin-bottom: 10px;
  width: 25vh;
  margin-bottom: 20px;
  margin-top: 10px;
}

button{
  border: 2px solid black;
  border-radius: 2vh;
  width: 8vh;
}
</style>