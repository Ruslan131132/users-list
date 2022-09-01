<template>
  <div id="app">
    <UserCards :users="users"/>
  </div>
</template>

<script>
import { ref } from 'vue'
import UserCards from "@/components/UserCards";
import usersData from '@/data/users.js'

export default {
  name: 'App',
  components: {
    UserCards
  },
  setup() {
    const users = ref(usersData)

    return { users }
  }
}
</script>

<style scoped>
#app{
  font-family: Roboto, sans-serif;
  font-size: 21px;
  font-weight: 400;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
}
</style>
