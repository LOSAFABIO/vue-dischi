<template>
  <div class="container-fluid m-0 d-flex">
    <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/image-gallery-spotify-logo-21.png" alt="">
  </div>
</template>

<script>
export default {
  name : "Header"
}
</script>

<style lang="scss" scoped>

@import "../assets/style/Vars.scss";

.container-fluid{
  height: 60px;
  background-color: $mainColor;
  justify-content: start;
  align-items: center;
}

img{
      height: 90%;
    }


</style>