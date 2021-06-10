<template>
  <div class="container-fluid">
      <div class="select d-flex justify-content-center">
        <select-genre :genres="genres" @searchGenre="searchAlbum"/>
    </div>
        <div class="container" v-if="!loading">
            <div class="element" v-for="(album,index) in filteredGenre" :key="index">
                <Album :item="album"/>
            </div>
        </div>
        <Loader v-else/>
  </div>
</template>

<script>
import Album from './Album.vue';
import Loader from './Loader.vue';
import axios from 'axios';
import SelectGenre from './SelectGenre.vue';

export default {
name: 'MusicList',
components: {
    Album,
    Loader,
    SelectGenre
},
data: function() {
    return {
        apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
        albums: [],
        selectedGenre: "",
        loading: true
    }
},
computed: {
    genres: function() {
        const newArray = [];
        this.albums.forEach((element) => {
            if (!newArray.includes(element.genre)) {
            newArray.push(element.genre);
            }
        })
        return newArray;
    },
    filteredGenre: function () {
        const newArray = this.albums.filter ((element) => {
            return element.genre.includes(this.selectedGenre)
        });
        return newArray;
    }
},
methods: {
    searchAlbum: function(text){
        this.selectedGenre = text;
    }
},
created: function() {
    axios
    .get (this.apiUrl)
    .then (
        (response) => {
            this.albums = response.data.response;
            this.loading = false;
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
        display: flex;
        flex-direction: column;

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