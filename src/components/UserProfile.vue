<template>
    <div class="card__profile">
    <img class="card__img" src="./../assets/logo.png" alt="">
    <div class="about__info">
      <h3 class="about__name">{{ user.name }}</h3>
      
      <p class="about__mail">Email : {{ user.email }}</p>
      <p class="about__phone">Phone : {{ user.phone }}</p>
      <h4>О себе {{ generateLoremIpsum(50) }}</h4>
      <p></p>
      <!-- Дополнительные данные профиля -->
    </div>
    </div>
  </template>
  
  <script>
 export default {
  name: 'UserProfile',
 props: {
  user: {
    type: Object,
    required: true
  }
 },
 methods: {
    generateLoremIpsum(length) {
      // Генерация рыбьего текста заданной длины
      const words = ['Lorem', 'ipsum', 'dolor', 'sit', 'amet', 'consectetur', 'adipiscing', 'elit'];
      let loremIpsum = '';
      
      for (let i = 0; i < length; i++) {
        const randomIndex = Math.floor(Math.random() * words.length);
        loremIpsum += words[randomIndex] + ' ';
      }
      
      return loremIpsum.trim();
    }
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