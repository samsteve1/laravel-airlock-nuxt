<template>
  <div>
    <p>Hello Sanctum</p>
    <button class="btn btn-primary" @click.prevent="login">Login</button>
  </div>
</template>

<script>
 import axios from 'axios'
export default {
  methods: {
   async login() {
    await axios.get('http://localhost:8000/sanctum/csrf-cookie')
      await axios.post('http://localhost:8000/login', {
        email: 'idowusteve@ymail.com',
        password: 'password'
      })

      let user = await axios.get('http://localhost:8000/api/user')
      console.log(user.data)
    }
  }
  
}
</script>

