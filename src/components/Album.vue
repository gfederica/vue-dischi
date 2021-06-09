<template>
  <div class=" album text-center">
    <img :src="item.poster" alt="" class="img-fluid">
    <h2>{{item.title}}</h2>
    <h3>{{item.author}}</h3>
    <h4>{{item.year}}</h4>
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

  .album {
    background-color: $lightGrey;
    margin: 0 15px;
    padding: 20px 0;
    @include flex-column-wrap;
    height: 280px;
  }

    img {
      height: 120px;
      margin-bottom: 14px;
    }
</style>