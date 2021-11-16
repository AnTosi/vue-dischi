<template>
    <div class="bg_bluegrey d-flex align-items-center">
        <img src="../assets/spot_logo.png" alt="">
        <label for="filter-genre" class="px-2">Filter albums by genre:</label>
        <select v-model="genre" @change="$emit('filter-genre', genre)" name="filter-genre" id="filter-genre">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>

export default {
    name: 'SiteHeader',

    data() {
        return {
            genre: ""
        }
    },

}

</script>

<style lang="scss">

@import '../assets/variables.scss';

    .bg_bluegrey {
        background: $bluegrey;
        height: 70px;
        img {
            height: 50px;
            margin-left: 10px;
            margin-right: 1rem;

        }
    }
    label  {
        background-color: white;
        border-top-left-radius: 5px;
        border-bottom-left-radius: 5px;

    }

    select {
        background-color: white;
        border-style: none;
        border-top-right-radius: 5px;
        border-bottom-right-radius: 5px;
        width: 80px;
        cursor: pointer;
    }

    
</style>
