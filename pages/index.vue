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
  font-size: 15px;
  font-weight: 400;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 320px 160px;
}


@media (min-width: 576px) and (max-width: 768px) {
  #app {
    font-size: 18px;
  }
}

@media (max-width: 1200px) {
  #app {
    padding: 100px 20px;
  }
}

@media (min-width: 1400px) {
  #app {
    font-size: 18px;
  }
}

@media (min-width: 1200px) and (max-width: 1600px) {
  #app {
    padding: 100px 50px;
  }
}

</style>
