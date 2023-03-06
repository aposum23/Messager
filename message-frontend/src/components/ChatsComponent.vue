<template>
  <div class="chats">
    <UserCardChatsComponent v-for="i in 13" class="card" @click="openChat(i)" v-if="show_chats"/>
  </div>
</template>

<script>
import UserCardChatsComponent from './UserCardChatsComponent.vue';

export default {
  name: 'ChatsComponent',
  components: {
    UserCardChatsComponent,
  },
  props:{
    show_chats: Boolean,
  },
  data(){
    return {
      user: [],
    }
  },
  methods:{
    openChat(chat_id){
      this.$emit('open-chat', chat_id);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .chats {
    overflow-y: scroll;
    overflow-x: hidden;
    background-color: #0F2632;
    width: 40rem;
    height:100vh;
  }
  .chats::-webkit-scrollbar {
    background-color: #0F2632;
    width: 10px;
  }

  .chats::-webkit-scrollbar-thumb {
    background-color: #1A2226;
    width: 10px;
  }
</style>
