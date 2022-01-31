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
    ListaDischi
  } 

}
</script>

<style lang="scss" scoped>

.container-dischi{
  // background-color: rgb(40, 42, 65);
  padding: 200px 0;
  height: 500px;
  width: 50%;
  margin: 0 auto;
}

</style>