<template>
    <div>
        <label for="filter-genre" class="px-2">Filter albums by genre:</label>
        <select v-model="genre" @change="$emit('filter-genre', genre)" name="filter-genre" id="filter-genre">
            <option value="all">All</option>
            <option value="rock">Rock</option>
            <option value="jazz">Jazz</option>
            <option value="pop">Pop</option>
            <option value="metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'Selector',

    data() {
        return {
            genre: ""
        }
    },
}
</script>