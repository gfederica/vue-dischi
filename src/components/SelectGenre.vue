<template>
    <select name="genre" v-model="selected" @change="$emit('searchGenre', selected)">
        <option value="" selected >Seleziona il genere..</option>
        <option v-for="(genre,index) in genres" :key="index" :value="genre">{{genre}}</option>
    </select>
</template>

<script>
export default {
    props: ['genres'],
    data() {
        return {
            selected: ''
        }
    }
}
</script>

<style scoped lang="scss">

@import "../style/general.scss";
@import "../style/mixins.scss";

    select {
        margin-top: 20px;
    }
</style>