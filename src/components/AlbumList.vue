<template>
    
</template>

<script>


export default {
    // components: { Loader },

    props: {
        genre: String
    },

    // data() {
    //     this.loading = true;
    //     return {
    //         music: [],
    //         API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
    //     };

    // },

    // mounted() {
    //     setTimeout(this.callApi, 3000);
    // },

    // methods: {
    //     // callApi() {
    //     //     axios
    //     //     .get(this.API_URL)
    //     //     .then((r) => {
    //     //         console.log(r.data);
    //     //         this.music = r.data.response;
    //     //         console.log(this.music);
    //     //         this.loading = false;
    //     //     })
    //     // },

    //     // logGenre(){
    //     //     console.log(this.genre);
    //     // }
    // },

    computed: {
        getFilteredGenre() {
            console.log(this.genre);
            return this.genre;
        }
    }
}


</script>

<style lang="scss">

// @import '../assets/variables.scss';

// .py_90 {
//     padding-top: 90px;
//     padding-bottom: 90px;
// }

// .album {
//     color: white;
//     &.card {
//         height: 360px;
//         width: 200px;
//         border-radius: 0;
//         background-color: $bluegrey;

//         img {
//         height: 160px;
//         width: 160px;
//         margin-right: auto;
//         margin-left: auto;
//         }

//         h3 {
//             font-weight: 700;
//             font-size: 1.3rem;
//         }

//     }

// }
</style>