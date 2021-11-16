<template>
    <div class="bg_bluegrey d-flex align-items-center">
        <img src="../assets/spot_logo.png" alt="">
        
    </div>
</template>

<script>

export default {
    name: 'SiteHeader',

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
