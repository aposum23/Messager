<template>
  <div class="page">
    <ChatsComponent/>
    <div class="chat">
      <ChatHeader @current_user="current_user"/>
      <ChatComponent v-if="show_empty_chat"/>
      <EmptyChatComponent v-if="show_empty_chat"/>
    </div>
  </div>
</template>

<script>
import ChatsComponent from './components/ChatsComponent.vue';
import ChatHeader from './components/ChatHeader.vue';
import ChatComponent from './components/ChatComponent.vue';
import EmptyChatComponent from './components/EmptyChatComponent.vue';

export default {
  name: 'App',
  components: {
    ChatsComponent,
    ChatHeader,
    ChatComponent,
    EmptyChatComponent,
  },
  data(){
    return{
      current_user: [],
      show_empty_chat: true,
    }
  },
  methods: {

  }
}
</script>

<style lang="scss">
@font-face {
  font-family: 'Montserrat';
  src: url('./assets/Montserrat-Regular.ttf');
}

body {
  margin: 0px;
  color: #fff;
  overflow:hidden;
  font-family: Montserrat;
}
.page {
  display: inline-flex;
  width:100%;
}
.chat {
  width:100%;
}
</style>
