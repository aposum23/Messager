<template>
  <div class="about-user">
    <div class="user-main">
      <img src=""/>
      <div class="user-main--name">
        <p class="user-name">User name</p>
        <P class="user-nick">@user_nick</P>
      </div>
    </div>
    <div class="user-description">
      <p class="deskription">
        This is example of user description.
         In this block he can write any information.
          For example he want to find new job or he do
           his own content chanel.
      </p>
    </div>
    <div class="user-contacts">
      <p>Other contacts:</p>
      <ul>
        <li v-for="i in 5">Contact {{ i }}: example of contact</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AboutUserComponent',
  data() {
    return{
      current_user: {},
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .about-user {
    width: 40%;
    height:50vh;
    background-color: #0F2632;
    border: 1px solid #0A1D27;
    border-right: 0px;
    border-radius: 15px;
    padding: 1rem;
    overflow-y: scroll;
  }

  .about-user::-webkit-scrollbar {
    background-color: #0F2632;
    width: 10px;
    border-radius: 0px 15px 15px 0px;
  }

  .about-user::-webkit-scrollbar-thumb {
    background-color: #1A2226;
    width: 10px;
    border-radius: 0px 15px 15px 0px;
  }

  .user-main {
    height:180px;
    width: 100%;
    & img {
      width: 180px;
      height: 180px;
      display: inline-block;
    }

    & .user-main--name {
      display: inline-block;
      float: right;
      width: 50%;
      height: 180px;
      text-align: center;

      & .user-name {
        font-size: 20px;
        margin-top: 4rem;
        margin-bottom: 0px; 
      }

      & .user-nick {
        margin-top: .1rem;
        color: #747474;
      }
    }
  }
</style>
