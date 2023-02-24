<template>
  <div class="messages-window">
    <div class="messages">
      <div v-for="i in 20">
        <br/>
        <br/>
        <div class="message-to">
          <p>Example of message</p>
        </div>
        <br/>
        <br/>
        <div class="message-from">
          <p>Example of message</p>
        </div>
      </div>
      <div class="wrap"></div>
      <div class="input-message">
        <input type="button" class="add-file"/>
        <input type="text" class="message-input"/>
        <input type="button" class="send-message"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatComponent',
  props: {
    chat_id: Number,
  },
  data() {
    return{
      current_user: {},
    }
  },
  methods:{
    scrollChatDown(){
      let div = document.getElementsByClassName('messages')[0];
      div.scrollTo(0, 2000);
      console.log('suck');
    }
  },
  mounted:
    function () {
      this.scrollChatDown();
    },
  beforeUpdate: 
    function () {
      this.scrollChatDown();
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  p {
    margin: 0px;
    padding: .5rem;
  }
  .message-to {
    display: inline-block;
    float: right;
    margin-left: auto;
    margin-right: .5rem;
    background-color: #28546b;
    border-radius: 15px;
    
    & p {
      clear: both;
    }
  }

  .message-from {
    display: inline-block;
    margin-left: .5rem;
    background-color: #1d4153;
    border-radius: 15px;
  }

  .messages {
    display:inline-block;
    width: 100%;
    height:95vh;
    overflow-y: scroll;
  }

  .messages::-webkit-scrollbar {
    background-color: #19313E;
    width: 10px;
  }

  .messages::-webkit-scrollbar-thumb {
    background-color: #1A2226;
    width: 10px;
  }

  .wrap {
    height:10rem;
  }

  .input-message {
    display: inline-flex;
    position:fixed;
    bottom: 2rem;
    left: 44%;
    .message-input {
      background-color: #0F2632;
      border: 1px solid #0A1D27;
      border-radius: 15px;
      width: 30rem;
      height: 2rem;
      padding: .5rem;
      margin: auto;
      color: #fff;
      font-size: 20px;
      outline-style: none;
    }

    .send-message {
      background-color: #0F2632;
      border: 1px solid #0A1D27;
      border-radius: 30px;
      width: 3rem;
      height: 3rem;
      margin-left: 1rem;
    }

    .send-message:active {
      background-color: #19313E;
      border: 1px solid #1d4153;
    }

    .add-file {
      background-color: #0F2632;
      border: 1px solid #0A1D27;
      border-radius: 30px;
      width: 3rem;
      height: 3rem;
      margin-right: 1rem;
    }

    .add-file:active {
      background-color: #19313E;
      border: 1px solid #1d4153;
    }
  }
</style>
