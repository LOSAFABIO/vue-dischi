<template>
  <div>
    <select 
    class="form-select" 
    v-model="select"
    @change="$emit(`filtra`, select)" >
        <option value="All">All</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <option value="Rock">Rock</option>
    </select>
  </div>
</template>

<script>
export default {
    name : "Genere",
    data() {
        return{
            select: ""
        }
    }
}

</script>

<style>


</style>