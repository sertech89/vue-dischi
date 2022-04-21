<template>
  <div class="albums">
      <AlbumComp
        v-for="(element, index) in albums"
        :key="index"
        :poster="element.poster"
        :title="element.title"
        :author="element.author"
        :year="element.year"
      />
  </div>
</template>

<script>
import axios from 'axios';
import AlbumComp from './partials/AlbumComp.vue';
export default {
  name: 'AlbumsComp',
  components: {
      AlbumComp
  },
  data() {
      return {
          albums: []
      }
  },
  created() {
      // chiamata API con Axios
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then( (res) => {
                this.albums = res.data.response;
                console.log(this.albums);
            });
  }
}
</script>

<style scoped lang="scss">
    @import '../style/variables.scss';
    .albums {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 10px;
    }
</style>