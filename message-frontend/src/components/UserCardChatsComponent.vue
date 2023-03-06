<template>
  <div class="user-card">
    <img class="user-image" src="@/assets/user_image.svg"/>
    <div class="user-text">
      <p>User Name</p>
      <p class="last-msg">This is last message</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'UserCardChatsComponent',
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
    & p{
      margin: .9rem;
    }

    & .last-msg {
      font-size: 14px;
      color: #747474;
    }
  }
</style>
