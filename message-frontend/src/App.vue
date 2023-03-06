<template>
  <div class="page">
    <div class="chats">
      <ChatsHeader @open-close-reg-card="openUserRegistration"/>
      <ChatsComponent @open-chat="openChat" :show_chats="user_is_auth"/>
    </div>
    <div class="chat">
      <ChatHeader @current_user="current_user" v-if="!show_empty_chat" @open-about="openAbout" />
      <ChatComponent @chat_id="user_chat_id" v-if="!show_empty_chat" />
      <EmptyChatComponent v-if="show_empty_chat" />
    </div>
    <AboutUserComponent class="about-user" v-if="show_about" />
    <AuthRegCardComponent v-if="show_reg_auth" class="auth-reg-card" />
  </div>
</template>

<script>
import ChatsComponent from './components/ChatsComponent.vue';
import ChatHeader from './components/ChatHeader.vue';
import ChatComponent from './components/ChatComponent.vue';
import EmptyChatComponent from './components/EmptyChatComponent.vue';
import AboutUserComponent from './components/AboutUserComponent.vue';
import ChatsHeader from './components/ChatsHeader.vue';
import AuthRegCardComponent from './components/AuthRegCardComponent.vue';

export default {
  name: 'App',
  components: {
    ChatsComponent,
    ChatHeader,
    ChatComponent,
    EmptyChatComponent,
    AboutUserComponent,
    ChatsHeader,
    AuthRegCardComponent,
  },
  data() {
    return {
      current_user: [],
      user_is_auth: false,
      show_empty_chat: true,
      user_chat_id: null,
      show_about: false,
      show_reg_auth: false,
    }
  },
  methods: {
    openChat(user_id) {
      if (user_id === this.user_chat_id || this.user_chat_id === null) {
        console.log(this.user_chat_id);
        this.show_empty_chat = !this.show_empty_chat;
        this.user_chat_id = user_id;
      }
      else {
        if (!this.show_empty_chat) {
          this.show_empty_chat = !this.show_empty_chat;
        }
        this.user_chat_id = user_id;
        this.show_empty_chat = !this.show_empty_chat;
      }
    },

    openAbout(user_id) {
      console.log(user_id);
      this.show_about = !this.show_about;
    },
    
    openUserRegistration(){
      this.show_reg_auth = !this.show_reg_auth;
    }
  },
  mounted:
    function(){
      let auth_key = window.localStorage.getItem('auth-key');

      console.log(auth_key);
      if (auth_key){
        this.user_is_auth = true;
      }
      else {
        this.show_reg_auth = true;
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
  overflow: hidden;
  font-family: Montserrat;
  background-color: #19313E;
}

.page {
  display: inline-flex;
  width: 100%;
}

.chat {
  width: 100%;
}

.about-user, .auth-reg-card {
  position: fixed;
  left: 50%;
  top: 20%;
}

.chats {
  display: block;
}
</style>
