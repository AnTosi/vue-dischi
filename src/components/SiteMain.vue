<template>
    <div class="bg_mainblue">
        <AlbumList />
    </div>
</template>

<script>
import AlbumList from './AlbumList.vue';

export default {
    name: 'SiteMain',
    components: {
        AlbumList
    }
}
</script>

<style lang="scss">
    @import '../assets/variables.scss';

    .bg_mainblue {
        background-color: $mainblue;
    }
</style>