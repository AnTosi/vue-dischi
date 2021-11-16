<template>
    <div>
        <label for="filter-author" class="px-2 ml_3 mt-3">Filter albums by author:</label>
        <select class="" v-model="author" @change="$emit('filter-author', author)" name="filter-author" id="filter-author">
            <option value="All">All</option>
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Queen">Queen</option>
            <option value="Sting">Sting</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
            <option value="Eric Clapton">Eric Clapton</option>
            <option value="Deep Purple">Deep Purple</option>
            <option value="Metallica">Metallica</option>
            <option value="Dave Weckl">Dave Weckl</option>
            <option value="Michael Jacjson">Michael Jacjson</option>
        </select>
    </div>
</template>

<script>

// import axios from 'axios';

export default {
    name: 'Selector',

    data() {
        return {

            // music: [],
            // API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
            // authors: [],
            author: ""
        }
    },


    // questa roba commentata è perché avevo pensato di fare un ciclo per le option con gli autori dall'API (che avrei dovuto pushare in un ulteriore array con if !includes per evitare ripetizioni), ma ancora una volta non ho fatto in tempo


    // mounted() {
    //     this.callApi
    // },

    // methods: {
    //     callApi() {
    //         axios
    //         .get(this.API_URL)
    //         .then((r) => {
    //             // console.log(r.data);
    //             this.music = r.data.response;
    //             // console.log(this.music);
    //             this.loading = false;
    //         })
    //     },
    // }
}
</script>

<style lang="scss">
    .ml_3 {
        margin-left: 1rem;
    }

    select {
        width: fit-content;
    }
    
    option {
        width: fit-content;
    }
</style>