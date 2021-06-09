<template>
  <div class="container-fluid">
      <div class="container">
        <div class="element" v-for="(album,index) in albums" :key="index">
            <Album :item="album"/>
        </div>
        </div>
  </div>
</template>

<script>
import Album from './Album.vue';
import axios from 'axios';

export default {
name: 'MusicList',
components: {
    Album
},
data: function() {
    return {
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        albums: []
    }
},
created: function() {
    axios
    .get (this.apiUrl)
    .then (
        (response) => {
            this.albums = response.data.response;
        }
    )
}
}
</script>

<style scoped lang="scss">

@import "../style/general.scss";
@import "../style/mixins.scss";

    .container-fluid {
        height: 90vh;
        background-color: $darkGrey;

        .container {
            width: 70%;
            @include flex;
            flex-wrap: wrap;
            height: 100%;
        }

        .element {
            width: 20%;
        }


    }
</style>