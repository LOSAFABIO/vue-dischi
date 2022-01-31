<template>
  <div class="albumDisco g-3 text-center">
      <img 
      :src="disco.poster" 
      alt=""
      class="img-fluid "
      >
      <h5 class="my-2 text">{{disco.title}}</h5>
      <p class="text">{{disco.author}} <br> {{disco.year}}</p>   
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

@import "../../assets/style/Vars.scss";

.albumDisco{
  margin: 10px 10px;
}

.text{
  color: white
}

p{
  opacity: 0.6;
}

</style>