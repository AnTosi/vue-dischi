<template>
    <div>
        <label for="filter-genre" class="px-2">Filter albums by genre:</label>
        <select v-model="genre" @change="filterGenre" name="filter-genre" id="filter-genre">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
        </select>
        <p>
            {{ filteredGenre }}
        </p>
    </div>
</template>

<script>
export default {
    
    data() {
        return {
            genre: ""
        };
    },
    computed: {
        filteredGenre() {
            return this.genre;
        } 
    }
}
</script>

<style lang="scss">
    p {
        color: white;
    }
</style>