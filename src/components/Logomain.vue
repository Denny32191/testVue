<template>
    <div class="header">
      <img class="header__logo" src="./../assets/Жилфонд.svg" alt="">
      <p class="header__user">Пользователь</p>
    </div>
</template>
<script>
export default {
  name: 'Header__main',
  data() {
    return {
      searchQuery: '', // Поле ввода для поискового запроса
      searchResults: [] // Результаты поиска из JSON
    };
  },
 
    
  
}
</script>
<style  lang="scss"  scoped>
.header{
   width: 100%;
   display: flex;
    justify-content: space-between;

}
.header__logo{
     margin-top: 40px;
   margin-bottom: 40px;
    margin-left: 10px;
}
.header__user{
    margin-top: 46px;

 }
 </style>