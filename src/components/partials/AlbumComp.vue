<template>
    <div class="album-container">
        <img :src="poster" alt="Album Cover">
        <h3 class="title">{{ title }}</h3>
        <div class="author">{{ author }}</div>
        <div class="year">{{ year }}</div>
    </div>
</template>

<script>
export default {
  name: 'AlbumComp',
  props: {
      poster: String,
      title: String,
      author: String,
      year: String
  }
}
</script>

<style scoped lang="scss">
    @import '../../style/variables.scss';
    .album-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: calc(100% / 6);
        background-color: $dark-gray;
        padding: 15px;
        text-align: center;
    }
    img {
        max-width: 100%;
    }
    .title {
        color: white;
        text-transform: uppercase;
        margin: 20px 0;
    }
    .year, .author {
        color: $text-gray;
        font-size: 17px;
    }
</style>