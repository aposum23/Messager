<template>
  <div class="page">
    <div class="chats">
      <ChatsHeader/>
      <ChatsComponent @open-chat="openChat"/>
    </div>
    <div class="chat">
      <ChatHeader @current_user="current_user" v-if="!show_empty_chat" @open-about="openAbout"/>
      <ChatComponent @chat_id="user_chat_id" v-if="!show_empty_chat"/>
      <EmptyChatComponent v-if="show_empty_chat"/>
    </div>
    <AboutUserComponent class="about-user" v-if="show_about"/>
  </div>
</template>

<script>
import ChatsComponent from './components/ChatsComponent.vue';
import ChatHeader from './components/ChatHeader.vue';
import ChatComponent from './components/ChatComponent.vue';
import EmptyChatComponent from './components/EmptyChatComponent.vue';
import AboutUserComponent from './components/AboutUserComponent.vue';
import ChatsHeader from './components/ChatsHeader.vue';

export default {
  name: 'App',
  components: {
    ChatsComponent,
    ChatHeader,
    ChatComponent,
    EmptyChatComponent,
    AboutUserComponent,
    ChatsHeader,
  },
  data(){
    return{
      current_user: [],
      show_empty_chat: true,
      user_chat_id: null,
      show_about: false,
    }
  },
  methods: {
    openChat(user_id){
      if (user_id === this.user_chat_id || this.user_chat_id === null){
        console.log(this.user_chat_id);
        this.show_empty_chat = !this.show_empty_chat;
        this.user_chat_id = user_id;
      }
      else {
        if (!this.show_empty_chat){
          this.show_empty_chat = !this.show_empty_chat;
        }
        this.user_chat_id = user_id;
        this.show_empty_chat = !this.show_empty_chat;
      }
    },

    openAbout(user_id){
      console.log(user_id);
      this.show_about = !this.show_about;
    }
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
  background-color: #19313E;
}
.page {
  display: inline-flex;
  width:100%;
}
.chat {
  width:100%;
}

.about-user{
  position:fixed;
  left: 50%;
  top:20%;
}

.chats {
  display: block;
}
</style>
