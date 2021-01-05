<template>
  <ul>
    <li v-for="user in users" :key="user.id">{{user.name}}</li>
  </ul>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return {
      users: []
    }
  },
  mounted(){
    axios.get('http://localhost:3000/api/users').then(res=>{
      console.log(res)
      this.users = res.data
    })
  }
}
</script>

<style>
</style>
