<template>
    <div>
        <label for="filter-genre" class="px-2">Filter albums by genre:</label>
        <select v-model="genre" @change="$emit('filter-genre', genre)" name="filter-genre" id="filter-genre">
            <option value="All">All</option>
            <option value="Rock">Rock</option>
            <option value="Jazz">Jazz</option>
            <option value="Pop">Pop</option>
            <option value="Metal">Metal</option>
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