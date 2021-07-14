<template>
  <main>

        <div class="left">
            <MoviesCard :movies="movieList"/>
        </div>

        <div class="right">
            <SeriesCard :series="seriesList"/>
        </div>
        
        
  </main>
</template>

<script>
import MoviesCard from "./MoviesCard.vue"
import SeriesCard from "./SeriesCard.vue"

export default {
    name: "Main",
    components: {
    MoviesCard,
    SeriesCard
  },
    props: {
       movieList: Array,
       seriesList: Array
    }
}
</script>

<style lang="scss">

@import "./../styles/vars.scss";

h2 {
    color: $netflixDarkRed;
    text-transform: uppercase;
    text-align: center;
    padding: 30px 0;
}

.left,
.right {
    width: 50%;
    float:left;
}

ul {
    width: 70%;
    margin:auto;
    list-style-type: none;
}

li.primary {
    font-size: 2rem;

    h3 {
        color: $netflixRed;
        font-size: 1.3rem;
    }
}

li.secondary {
    font-size: 1.3rem;
    padding:20px;

    span {
        font-weight: 800;
    }
}

</style>

++++++++++NOTE++++++++++
API con i popular: "https://api.themoviedb.org/3/movie/popular?api_key=498d1c8d4b0a878ee9fc00ed9888ae18"