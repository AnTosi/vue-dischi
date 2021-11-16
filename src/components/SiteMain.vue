<template>
    <div class="bg_mainblue">
        <Selector @filter-genre="filterGenre"/>
        <SelectorAuthor @filter-author="filterAuthor"/>
        <div class="justify-content-center d-flex flex-wrap py_90">
            <div v-show="loading">
                <Loader/>
            </div>
            <div class="album py-2 card text-center py-3 px-3 mx-3 my-2" v-for="album in music" :key="album.title">
                <img v-bind:src="album.poster" v-bind:alt="album.title">
                <h3 class="my-3 px-2">
                    {{album.title.toUpperCase()}}
                </h3>

                <p class="my-0 text-muted">
                    {{album.author}}
                </p>

                <p class="my-0 text-muted">
                    {{album.year}}
                </p>
            </div>     
        </div>
    </div>
</template>

<script>
import axios from 'axios';
import Loader from './Loader.vue';
import Selector from './Selector.vue';
import SelectorAuthor from './SelectorAuthor.vue'

export default {
    name: 'SiteMain',
    components: {
        Selector,
        Loader,
        SelectorAuthor
    },
    
    data() {
        this.loading = true;
        return {
            music: [],
            API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
            // filterByGenre: "",
        };

    },

    mounted() {
        setTimeout(this.callApi, 3000);
    },


    // computed: {
    //     getFilteredGenre(genre) {
    //         if (genre == 'All') {
    //             return this.music
    //         } else {
    //             console.log(genre);
    //             const filteredGenre = this.music.filter(album => {
    //             return album.genre.includes(genre)}
    //             );
    //             return filteredGenre
    //         }

        //in questo caso la ricerca andava fatta con la computed property ma non ho avuto abbastanza tempo per farlo


    methods: {

        filterGenre(genre) {
            if (genre == 'All') {
                return this.callApi()
            } else {
                //non posso cercare tra tutti ma solo tra i già filtrati, non faccio in tempo a debuggare
                console.log(genre);
                const filteredGenre = this.music.filter(album => {
                return album.genre.includes(genre)}
                );
                this.music = filteredGenre;
            }
        },
            // this.filteredGenre = genre;
        // },

        filterAuthor(author) {
            if (author == 'All') {
                return this.callApi()
            } else {
                //non posso cercare tra tutti ma solo tra i già filtrati, non faccio in tempo a debuggare
                console.log(author);
                const filteredAuthor = this.music.filter(album => {
                return album.author.includes(author)}
                );
                this.music = filteredAuthor;
            }
        },

        callApi() {
            axios
            .get(this.API_URL)
            .then((r) => {
                // console.log(r.data);
                this.music = r.data.response;
                // console.log(this.music);
                this.loading = false;
                // console.log(this.music.genre);
            })
        },

    }

}
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .bg_mainblue {
        background-color: $mainblue;
    }


    .py_90 {
        padding-top: 90px;
        padding-bottom: 90px;
    }

    .album {
        color: white;
        &.card {
            height: 360px;
            width: 200px;
            border-radius: 0;
            background-color: $bluegrey;

            img {
            height: 160px;
            width: 160px;
            margin-right: auto;
            margin-left: auto;
            }

            h3 {
                font-weight: 700;
                font-size: 1.3rem;
            }

        }

    }
</style>