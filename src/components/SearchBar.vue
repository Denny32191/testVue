<template>
  <div class="menu__staff">
    <h2>Поиск Сотрудников</h2> <!-- Заголовок раздела поиска сотрудников -->
    <input class="input__search" v-model="searchQuery" @input="handleSearch" type="text" placeholder="Search" >  <!--Обработчик события input, вызывает метод handleSearch --> <!-- Плейсхолдер для поля ввода -->
    
    <ul v-if="searchQuery">
      <li  v-for="user in filteredUsers" :key="user.id"  @click="handleClick(user)" >
        <img src="./../../src/assets/logo.png" alt="">
        <p > {{ user.name }} {{ user.email }}</p>
        
      </li> <!-- Отображение отфильтрованных пользователей в виде списка -->
    </ul>
    <p v-if="searchQuery && filteredUsers.length === 0">Ничего не найдено.</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      users: [], // Пустой массив для хранения пользователей
      searchQuery: '', // Переменная для хранения значения из поля ввода поиска
      filteredUsers: [], // Пустой массив для хранения отфильтрованных пользователей
      selectedUserData: null // Добавленное свойство для хранения данных выбранного пользователя
    };
  },
  mounted() {
    this.fetchUsers(); // Вызов метода для загрузки пользователей при монтировании компонента
  },
  methods: {
    fetchUsers() {
      fetch('https://jsonplaceholder.typicode.com/users') // Запрос к API для получения списка пользователей
        .then(response => response.json()) // Преобразование ответа в JSON формат
        .then(data => {
          this.users = data; // Сохранение полученного списка пользователей в переменную users
        })
        .catch(error => {
          console.error(error); // Обработка ошибки, если запрос не удался
        });
    },
    handleSearch() {
      const filteredUsers = this.users.filter(user => {
        return (
          user.name.toLowerCase().includes(this.searchQuery.toLowerCase()) || // Фильтрация пользователей по имени
          user.email.toLowerCase().includes(this.searchQuery.toLowerCase()) // Фильтрация пользователей по mail пользователя
        );
      });
      this.filteredUsers = filteredUsers; // Сохранение отфильтрованных пользователей в переменную filteredUsers
      this.$emit('searchResults', filteredUsers); // Генерация пользовательского события searchResults с отфильтрованными пользователями в качестве данных
    },
    handleClick(user) {
      this.selectedUserData = user;
      this.$emit('userSelected', user);
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only npm run serve -->
<style lang="scss"  scoped>
img {
  width: 50px;
  height: 50px;
}
li{
  display: flex;
  align-items: center;
  flex-direction: center;
  justify-content: space-between;
  cursor: pointer;
  :hover {
    background-color: bisque;
  }
}
p {
  width: 220px;
  height: 60px;
  display: flex;
  
  align-items: center;
  border-radius: 10px;
  padding-left: 30px;
  cursor: pointer;
  :hover {
    background-color: bisque;
 }
}
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
  .menu_search{
    width: 200px;
    height: 200px;
  }
</style>
