<template>
    <div>
        <div class="albums" v-if="!loadingStatus">
            <AlbumComp v-for="(element, index) in updateAlbums" :key="index" :poster="element.poster"
                :title="element.title" :author="element.author" :year="element.year" />
        </div>
        <div v-else>
            <LoaderComp />
        </div>
    </div>
</template>

<script>
    import axios from 'axios';
    import AlbumComp from './partials/AlbumComp.vue';
    import LoaderComp from './partials/LoaderComp.vue';

    export default {
        name: 'AlbumsComp',
        props: ['genre'],
        components: {
            AlbumComp,
            LoaderComp
        },
        data() {
            return {
                albums: [],
                loadingStatus: false,
                selectedGenre: ''
            }
        },
        created() {
            // chiamata API con Axios
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then((res) => {
                    this.albums = res.data.response;
                    console.log(this.albums);
                    this.loadingStatus = false;
                });
        },
        computed: {
            /* Aggiorna l'elenco degli album in base al genere scelto */
            updateAlbums() {
                if (this.genre == 'all') {
                    return this.albums;
                }
                return this.albums.filter((item) => {
                    return item.genre.toLowerCase().includes(this.genre);
                })
            }
        },
    }
</script>

<style scoped lang="scss">
    @import '../style/variables.scss';

    .albums {
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        gap: 20px 30px;
    }
</style>