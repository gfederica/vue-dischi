<template>
  <div id="app">
    <Header/>
    <MusicList/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import MusicList from './components/MusicList.vue'

export default {
  name: 'App',
  components: {
    Header,
    MusicList
  }
}
</script>

<style lang="scss">
@import '~bootstrap/scss/bootstrap';
@import "./style/general.scss";


</style>
