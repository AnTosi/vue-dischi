<template>
    <div class="bg_bluegrey">
        <img src="../assets/spot_logo.png" alt="">
    </div>
</template>

<script>

export default {
    name: 'SiteHeader'
}
</script>

<style lang="scss">

@import '../assets/variables.scss';

    .bg_bluegrey {
        background: $bluegrey;
        height: 70px;
        img {
            height: 50px;
            margin-top: 10px;
            margin-left: 10px;
        }
    }
</style>
