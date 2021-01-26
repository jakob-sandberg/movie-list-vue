<template>
  <div id="app">

    <router-view @add-new-movie="addMovieToMovies" />
  </div>
</template>

<script>
export default {
  data() {
    return{
      movies: [],
    }
  },

  methods: {
    addMovieToMovies(newMovie) {
      this.movies.push(newMovie);
      console.log("In app.vue:", this.movies);
    }
  }
}
</script>

<style>
