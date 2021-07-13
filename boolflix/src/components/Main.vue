<template>
  <main>

      <div class="left">
          <h2>Film</h2>

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
                      <span>voto: </span> {{movie.vote_average}}
                  </li>
              </ul>

          </li>
        </ul>
      </div>

        <div class="right">
            <h2>Serie TV</h2>
        <ul v-for="(serie, i) in seriesList" :key="i">
            <li class="primary"> 
              
              <h3>{{serie.name}}</h3>

              <ul>
                  <li class="secondary" v-if="serie.overview != ''">
                      <span>Trama:</span> {{serie.overview}}
                  </li>
                  <li class="secondary">
                      <span>Titolo originale:</span> {{serie.original_name}}
                  </li>
                  <li class="secondary">
                      <span>Lingua originale:</span> {{serie.original_language}}
                  </li>
                  <li class="secondary">
                      <span>voto: </span> {{serie.vote_average}}
                  </li>
              </ul>

          </li>
        </ul>
        </div>
  </main>
</template>

<script>


export default {
    name: "Main",
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