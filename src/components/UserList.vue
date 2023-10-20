<template>
    <div>
        <h3>Результат</h3>
      <ul >
        <li  v-for="user in users" :key="user.id" @click="selectUser(user)">
          {{ user.name }}
          <img src="" alt="">
          <h4></h4>
          <p></p>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['users'],
    methods: {
      selectUser(user) {
        this.$emit('select-user', user);
      }
    }
  }
  </script>
  <style lang="scss"  scoped>

</style>