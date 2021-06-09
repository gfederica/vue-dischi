<template>
  <div class="loader">
      <img src="../assets/spotify2.gif" alt="">
  </div>
</template>

<script>
export default {
    name: 'Loader'
}
</script>

<style scoped lang="scss">

@import "../style/mixins.scss";

    .loader {
        background-color: #F9F9F9;
        width: 100%;
        height: 90vh;
        @include flex;

        & img {
            height: 100%;
            
        }
    }
</style>