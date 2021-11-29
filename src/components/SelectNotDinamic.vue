<template>
  <select v-model="genreSelect" @change="$emit('genre', genreSelect)">
      <option value=""></option>
      <option value="Rock">Rock</option>
      <option value="Pop">Pop</option>
      <option value="Jazz">Jazz</option>
      <option value="Metal">Metal</option>
  </select>
</template>

<script>
export default {
    name: 'SelectNotDinamic',
    data() {
        return {
            genreSelect: "",
        }
    }
    
}
</script>

<style lang="scss" scoped>

</style>