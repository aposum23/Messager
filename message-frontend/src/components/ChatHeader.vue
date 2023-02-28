<template>
  <div class="user-card" @click="openAbout()">
    <img class="user-image" src=""/>
    <div class="user-text">
      <p>User name</p>
      <p class="status-online">online</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatHeader',
  data() {
    return{
      current_user: {},
      user_id: 1,
    }
  },
  methods:{
    openAbout(){
      this.$emit('open-about', this.user_id);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .user-card {
    width: 100%;
    height: 5rem;
    display: inline-flex;
    background-color: #0F2632;
    border: 1px solid #0A1D27;
    border-left: none;

    & img {
      width: 50px;
      height: 50px;
      margin: auto .5rem;
    }
  }

  .user-card:active {
    background-color: #152E3C;
  }

  .user-text {
    margin-top: .2rem;
    & p{
      margin: .6rem;
    }

    & .status-online {
      font-size: 14px;
      color: #747474;
    }
  }
</style>
