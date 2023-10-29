<template>
  <div class="wrapper">
    <Logomain />
    <div class="maincontent">
      <div class="menu">
      <SearchBar @userSelected="selectUser" />
      <UserList  />
      </div>
      <UserProfile :user="selectedUser" v-if="selectedUser" />
    </div>
    
  </div>
</template>

<script>
import SearchBar from "./components/SearchBar.vue";
import Logomain from "./components/Logomain.vue";
import UserList from "./components/UserList.vue";
import UserProfile from "./components/UserProfile.vue"


export default {
  name: "App",
  components: {
    Logomain,
    SearchBar,
    UserList,
    UserProfile

  },
  data() {
    return {
      selectedUser: null
    };
  },
  methods: {
    selectUser(user) {
      this.selectedUser = user;
    }
  }
};
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Serif:ital,wght@0,300;0,400;0,600;1,500;1,700&family=Open+Sans:ital,wght@0,400;0,600;1,400&display=swap');
.maincontent {
  border-radius: 10px;
  min-width: 1266px;
  min-height: 575px;
  display: flex;
  border: 1px solid rgba(182, 175, 175, 0.5);
}
.menu{
     min-width: 262px;
   background: rgba(253, 253, 253, 1);
    border-right: 1px solid rgba(182, 175, 175, 0.5);
  padding-left: 10px;
}
</style>
