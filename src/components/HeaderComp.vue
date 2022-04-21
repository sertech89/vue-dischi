
   
<template>
  <header>
      <img class="logo" src="../assets/img/spotify-logo.webp" alt="Spotify Logo">
  </header>
</template>

<script>
export default {
  name: 'HeaderComp'
}
</script>

<style scoped lang="scss">
    @import '../style/variables.scss';
    header {
        height: 70px;
        background-color: $dark-gray;
        padding: 10px;
    }
    .logo {
        width: 50px;
    }
</style>