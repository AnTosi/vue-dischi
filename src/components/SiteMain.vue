<template>
    <div class="bg_mainblue">
        <button @click="logGenre">
            bubbo
        </button>
        <label for="filter-genre" class="px-2">Filter albums by genre:</label>
        <select v-model="genre" @change="$emit('filter-genre', genre)" name="filter-genre" id="filter-genre">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
        </select>
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