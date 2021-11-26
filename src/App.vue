<template>
    <div id="app">
        <!-- HEADER -->
        <Header :allGenres="genresCollection"
        @genreSelect="genreChosen" />

        <!-- MAIN -->
        <main>
            <AlbumSection :Albums="filterGenres" />
        </main>
    </div>
</template>

<script>
import Header from '@/components/Header.vue';
import AlbumSection from '@/components/AlbumSection.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Header,
    AlbumSection,
  },
  data() {
        return {
            albumCollection: null,
            Genres: '',
            genresCollection: [],
        };
  },
  computed: {
    filterGenres() {
      if (this.Genres === '') {
        return this.albumCollection;
      }

      return this.albumCollection.filter(item => {
        return item.genre.toLowerCase().includes(this.Genres.toLowerCase())
      });
    }
  },
  created() {
        this.getAlbum();
  },
  methods: {
      getAlbum() {
          /* Call API for data */
          axios
              .get('https://flynn.boolean.careers/exercises/api/array/music')
              .then(result => {
                  this.albumCollection = result.data.response;
                  this.selectGenreTypes();
              })
              .catch(error => console.log(error));

      },
      genreChosen(genre) {
          this.Genres = genre;
      },
      selectGenreTypes() {
        this.albumCollection.forEach(element => {
          if (!this.genresCollection.includes(element.genre) ) {
              this.genresCollection.push(element.genre);
          }
        });
        
          console.log(this.genresCollection);
      }
  }
}
</script>

<style lang="scss">
@import '@/styles/Generals.scss';
</style>
