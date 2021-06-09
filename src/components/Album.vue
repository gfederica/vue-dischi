<template>
  <div class="text-center">
    <img :src="item.poster" alt="" class="img-fluid">
      
  </div>
</template>

<script>

export default {
  name: 'Album',
  props: ["item"]
}
</script>

<style scoped lang="scss">

@import "../style/general.scss";
@import "../style/mixins.scss";

    img {
      height: 100px;
    }
</style>