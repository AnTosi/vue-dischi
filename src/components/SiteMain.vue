<template>
    <div class="bg_mainblue">
        <button @click="logGenre">
            bubbo
        </button>
        <AlbumList />
    </div>
</template>

<script>
import AlbumList from './AlbumList.vue';

export default {
    name: 'SiteMain',
    components: {
        AlbumList
    },

    props: {
        genre: String
    },

    methods: {
        logGenre(genre) {
            console.log(genre);
        }   
    }

}
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .bg_mainblue {
        background-color: $mainblue;
    }
</style>