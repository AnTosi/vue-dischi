<template>
    <div class="bg_mainblue">
        <button @click="logGenre">
            bubbo
        </button>
        <Selector />
        <AlbumList />
    </div>
</template>

<script>
import AlbumList from './AlbumList.vue';
import Selector from './Selector.vue';

export default {
    name: 'SiteMain',
    components: {
        AlbumList,
        Selector
    },
    
    data() {
        return {
            genre: ""
        }
    },

    methods: {

        logGenre() {
            console.log(this.genre);
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