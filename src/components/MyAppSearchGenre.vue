<template>
    <div>
        <select v-model="searchGenre" class="form-select" aria-label="" @change="$emit('filterGenre', searchGenre)" >
            <option selected></option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
        </select>
    </div>
</template>

<script>
export default {
    name: 'MyAppSearchGenre',
    data() {
        return {
            searchGenre: '',
        }
    }
}


</script>

<style scoped lang="scss">

</style>