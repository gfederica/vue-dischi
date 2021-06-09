<template>
  <header>
    <img src="../assets/spotify.png" alt="logo">
  </header>
</template>

<script>
export default {
  name: 'Header'
}
</script>


<style scoped lang="scss">
@import "../style/general.scss";
@import "../style/mixins.scss";

  header {
    height: 10vh;
    background-color: $lightGrey;
    @include flex-vertical-only;

    img {
      height: 80%;
      margin-left: 10px;
    }
  }
</style>
