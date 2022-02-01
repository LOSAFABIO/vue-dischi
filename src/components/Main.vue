<template>
  <div class="container-fluid p-0 m-0">
    <div class="row">
      <div class="col">
       
        <ListaDischi />
      </div>
    </div>
  </div>
</template>

<script>

import ListaDischi from "./sections/ListaDischi.vue";

export default {
  name       : "Main",
  components : {
    ListaDischi,
  } 

}
</script>

<style lang="scss" scoped>

@import "../assets/style/Vars.scss";

.row{
  background-color: $thirdColor;
}


</style>