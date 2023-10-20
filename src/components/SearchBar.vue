<template>
  
 
    <div class="menu__staff">
    <h2>Поиск Сотрудников</h2>
    <input class="input__search" type="text" v-model="searchInput" @input="searchUsers" placeholder="Введите id или имя">
    <ul>
      <li v-for="user in users" :key="user.id" @click="selectUser(user)">
        {{ user.name }}
      </li>
    </ul>
  </div>
</template>



<script>
export default {
  data() {
    return {
      searchInput: '',
      users: []
    }
  },
  methods: {
    searchUsers() {
      // Здесь выполняйте запрос к API с использованием this.searchInput
      // Обновляйте this.users с результатами поиска
    },
    selectUser(user) {
      // Выбранный пользователь передается в родительский компонент через $emit
      this.$emit('select-user', user);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only npm run serve -->
<style lang="scss"  scoped>
.menu{
     min-width: 262px;
   background: rgba(253, 253, 253, 1);
    border-right: 1px solid rgba(182, 175, 175, 0.5);
  padding-left: 10px;
}
 .input__search{
    margin-bottom: 20px;
   width: 240px;
    height: 40px;
 }
  
 .menu__staff{
    margin-top: 20px;

  }
</style>
