<template>
    <div class="row">
        <div class="col-2 album" v-for="album in music" :key="album.title">
            <p>
                {{album.title}}
            </p>
        </div>        
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            music: [],
            API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
        };
    },

    mounted() {
        setTimeout(this.callApi, 3000);
    },

    methods: {
        callApi() {
            axios
            .get(this.API_URL)
            .then((r) => {
                console.log(r.data);
                this.music = r.data.response;
                console.log(this.music);
                // this.loading = false;
            })
        }
    }
}


</script>

<style lang="scss">
    .album {
        color: white;
    }
</style>