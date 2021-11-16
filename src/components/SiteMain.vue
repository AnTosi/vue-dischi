<template>
    <div class="bg_mainblue">
        <Selector @filter-genre="filterGenre"/>
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

export default {
    name: 'SiteMain',
    components: {
        Selector,
        Loader
    },
    
    data() {
        this.loading = true;
        return {
            music: [],
            API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
        };

    },

    mounted() {
        setTimeout(this.callApi, 3000);
    },

    methods: {

        filterGenre(genre) {
            if (genre == 'All') {
                this.callApi()
            } else {
                console.log(genre);
                const filteredGenre = this.music.filter(album => {
                return album.genre.includes(genre)}
                );
                this.music = filteredGenre;
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
                console.log(this.music.genre);
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