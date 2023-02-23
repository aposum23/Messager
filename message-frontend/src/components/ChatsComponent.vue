<template>
  <div class="chats">
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
    <UserCardChatsComponent class="card"/>
  </div>
</template>

<script>
import UserCardChatsComponent from './UserCardChatsComponent.vue';

export default {
  name: 'ChatsComponent',
  components: {
    UserCardChatsComponent
  },
  data(){
    return {
      user: [],
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .chats {
    overflow-y: scroll;
    overflow-x: hidden;
    width: 40rem;
    height:100vh;
  }
  .chats::-webkit-scrollbar {
    background-color: #19313E;
    width: 10px;
  }

  .chats::-webkit-scrollbar-thumb {
    background-color: #1A2226;
    width: 10px;
  }
</style>
