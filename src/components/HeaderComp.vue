<template>
  <header>
    <img class="logo" src="../assets/img/spotify-logo.webp" alt="Spotify Logo">


    <!-- Filtro in base al genere -->
    <select v-model="selectedGenre" @change="$emit('selectGenre', selectedGenre)" name="genre" id="genre">
      <option value="all" selected="selected">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </header>
</template>

<script>
  export default {
    name: 'HeaderComp',
    data() {
      return {
        selectedGenre: '',
      }
    }
  }
</script>

<style scoped lang="scss">
  @import '../style/variables.scss';

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 70px;
    background-color: $dark-gray;
    padding: 10px;
  }

  .logo {
    width: 50px;
  }

  select {
      height: 30px;
      width: 100px;
    }
</style>