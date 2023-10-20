<template>
  <div class="wrapper">
    <Logomain />
    <div class="maincontent">
      <div class="menu">
      <SearchBar />
      <UserList />
      </div>
      <UserProfile/>
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
};
</script>

<style lang="scss" scoped>
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
