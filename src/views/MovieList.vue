<template>
  <div class="movie-list">
    <div v-if="movies.length > 0">
    <MovieCard  v-for="(movie, i) in movies" :key="i" :movie="movie" />
  </div>
  </div>
</template>

<script>
import MovieCard from "./MovieCard";

export default {

components: {
  MovieCard
},

props: ["newMovie"],

watch: {
  newMovie: function(newMovie, oldMovie) {
    console.log("old Movie:", oldMovie);
     console.log("New Movie:", newMovie);
     this.movies.unshift(newMovie)
  }
},

  data() {
    return{
      movies: [{
        title: "Harry P",
        rating: 4,
        genre: "FANTASY",
        desc: "Lorem Upsum",
      },
      {
      title: "James Bond",
        rating: 3,
        genre: "Action",
        desc: "Lorem Upsum",
        }
      ],
      
    }
  },
methods: {
    addMovieToMovies(newMovie) {
      this.movies.push(newMovie);
      console.log("In App.vue - movies: ", this.movies);
    },
}

}
</script>

<style>

</style>