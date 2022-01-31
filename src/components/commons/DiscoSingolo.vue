<template>
  <div class="container text-center">
      <img 
      :src="disco.poster" 
      alt=""
      class="img-fluid m-3"
      >
      <h3>{{disco.title}}</h3>
      <h5>{{disco.author}}</h5>
      <h5>{{disco.year}}</h5>     
  </div>
</template>

<script>

export default {
    name  : "DiscoSingolo",
    props : {
      disco : Object
    }
}
</script>

<style>

</style>