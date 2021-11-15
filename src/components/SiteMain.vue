<template>
    <div class="bg_mainblue d-flex flex-wrap">
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
        height: 600px;
    }
</style>