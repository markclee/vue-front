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
    // 此处等于 http://121.36.36.62:3000/api/users
    axios.get('/api/users').then(res=>{
      console.log(res)
      this.users = res.data
      console.log('构建')
    })
  }
}
</script>

<style>
</style>
