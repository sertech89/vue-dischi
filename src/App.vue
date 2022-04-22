<template>
  <div id="app">
    <HeaderComp @selectGenre="filterGenre" />

    <main>
      <div class="container">
        <AlbumsComp :genre="selectedGenre" />
      </div>
    </main>
  </div>
</template>

<script>
  import HeaderComp from './components/HeaderComp.vue';
  import AlbumsComp from './components/AlbumsComp.vue';
  export default {
    name: 'App',
    components: {
      HeaderComp,
      AlbumsComp
    },
    data() {
      return {
        selectedGenre: 'all'
      }
    },
    methods: {
      filterGenre(genre) {
        this.selectedGenre = genre;
      }
    },
  }
</script>

<style lang="scss">
  @import './style/variables.scss';

  // Reset
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
  }

  main {
    background: $dark-blue;
    height: 120vh;
    padding: 40px 0;
  }

  .container {
    width: 70%;
    margin: 0 auto;
  }
</style>