<template>
  <main>

      <ul v-for="(movie, i) in movieList" :key="i">
            <li class="primary"> 
              
              <h3>{{movie.title}}</h3>

              <ul>
                  <li class="secondary" v-if="movie.overview != ''">
                      <span>Trama:</span> {{movie.overview}}
                  </li>
                  <li class="secondary">
                      <span>Titolo originale:</span> {{movie.original_title}}
                  </li>
                  <li class="secondary">
                      <span>Lingua originale:</span> {{movie.original_language}}
                  </li>
                  <li class="secondary">
                      <span>voto:</span> {{movie.vote_average}}
                  </li>
              </ul>

          </li>
        </ul>
  </main>
</template>

<script>


export default {
    name: "Main",
    props: {
       movieList: Array
    }
}
</script>

<style lang="scss">

@import "./../styles/vars.scss";

ul {
    width: 70%;
    margin:auto;
    list-style-type: none;
}

li.primary {
    font-size: 1.8rem;

    h3 {
        color: $netflixRed;
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