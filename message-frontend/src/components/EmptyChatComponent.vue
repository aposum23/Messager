<template>
  <div class="messages-window">
    <div class="messages">
    </div>
  </div>
</template>

<script>
export default {
  name: 'EmptyChatComponent',
  data() {
    return{
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  p {
    margin: 0px;
    padding: .5rem;
  }

  .messages {
    display:inline-block;
    width: 100%;
    height:95vh;
    background-color: #19313E;
  }
</style>
