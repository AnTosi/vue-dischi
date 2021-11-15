<template>
    <div>

    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            characters: [],
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
                // this.loading = false;
            })
        }
    }
}


</script>