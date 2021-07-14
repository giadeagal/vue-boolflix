<template>
  <section>
      <h2>Film</h2>

            <ul v-for="(movie, i) in movies" :key="i">
                <li class="primary"> 
              
                    <h3>{{movie.title}}</h3>

                    <ul>
                        <li class="secondary" v-if="movie.overview != ''">
                            <span>Trama:</span> {{movie.overview}}
                        </li>
                        <li class="secondary" v-if="movie.overview == ''">
                            <small>Trama non disponibile</small>
                        </li>
                        <li class="secondary">
                            <span>Titolo originale:</span> {{movie.original_title}}
                        </li>
                        <li class="secondary">
                            <span>Lingua originale:</span> {{movie.original_language}}
                        </li>
                        <li v-if="movie.vote_average!=0" class="secondary">
                            <span>voto: </span> {{movie.vote_average}}
                        </li>
                        <li v-if="movie.vote_average==0" class="secondary">
                            <small>voto non disponibile </small>
                        </li>
                    </ul>
              
              
                </li>
            </ul>
  </section>
</template>

<script>
export default {
    name: "MoviesCard",
    props: {
        movies: Array
    }
}
</script>

<style>

</style>