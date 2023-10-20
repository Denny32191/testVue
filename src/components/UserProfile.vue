<template>
    <div class="card__profile">
    <img class="card__img" src="" alt="">
    <div class="about__info">
      <h3 class="about__name">Ervin Howwel</h3>
      <p class="about__mail">Email Shanna@melissa.tv</p>
      <p class="about__phone">Phone 010-692-6593 x09125</p>
      <h4>О себе</h4>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Esse consectetur doloremque veniam! Voluptate placeat blanditiis dolores quia 
        ad impedit labore dolor sint maiores quas. Aliquid eos saepe odit vitae esse?</p>
      <!-- Дополнительные данные профиля -->
    </div>
    </div>
  </template>
  
  <script>
 export default {
  name: 'UserProfile',
  data() {
    return {
      searchQuery: '', // Поле ввода для поискового запроса
      searchResults: [] // Результаты поиска из JSON
    };
  }
}
  </script>
  <style ang="scss"  scoped>
.card__profile{
    display: flex;
}
.card__img{
    width: 424px;
    height: 286px;
    padding-left: 20px;
    margin-top: 20px;
}
.about__name {
    padding-top: 24px;
}
.about__info{
    display: flex;

    flex-direction: column;
    margin-left: 30px;
    width: 22rem;
    height: 25rem;
}
</style>