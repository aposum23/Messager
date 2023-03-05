<template>
  <div class="find">
    <img class="user-image" src="" @click="openCloseRegCard"/>
    <div class="find-div">
      <img src="@/assets/search.svg"/>
      <input type="text">
    </div>
  </div>
</template>

<script>
export default {
  name: 'ChatsHeader',
  data() {
    return{
      user_id: 1,
    }
  },
  methods:{
    openCloseRegCard(){
      this.$emit('open-close-reg-card');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  .find {
    width: 100%;
    height: 5rem;
    display: inline-flex;
    background-color: #0F2632;
    border: 1px solid #0A1D27;

    & img {
      width: 35px;
      height: 35px;
      margin-left: 1rem;
      margin-top:auto;
      margin-bottom: auto;
    }
  }

  .find-div {
    height: 1.25rem;
    margin: auto;
    width: 65%;
    background-color: #0A1D27;
    padding: .1rem;

    & img {
      width: 21px;
      height: 21px;
      margin-left: .1rem;
    }

    & input {
      float: right;
      width: 90%;
      outline: none;
      background-color: #0A1D27;
      border: none;
      color:#fff;
    }
  }
</style>
