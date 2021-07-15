<template>
  <section>
      <h2>Film</h2>

      <div class="container">
          <div class="row">
              <div class="col-4 g-3 hover-here" v-for="(movie, i) in movies" :key="i">
                  <div class="card bg-dark text-white" >
                  <img :src="`https://image.tmdb.org/t/p/w342/${movie.poster_path}`" :alt="movie.title" class="card-img">
                  <div class="card-img-overlay">
                    <h3 class="card-title hover-txt">{{movie.title}}</h3>
                    <p class="card-text">
                        <ul class="hover-txt">
                            <li v-if="movie.overview != ''">
                                <strong>Trama:</strong> {{movie.overview}}
                            </li>
                            <li class="secondary" v-if="movie.overview == ''">
                                <small>Trama non disponibile</small>
                            </li>
                            <li class="secondary">
                                <strong>Titolo originale:</strong> {{movie.original_title}}
                            </li>
                            <li class="secondary">
                                <strong>Lingua originale: </strong> 

                                <img class="flag"
                                v-if="flags.includes(movie.original_language)"

                                :src="
                                    require(`../assets/flags/${movie.original_language}.png`)
                                " 
                                :alt="movie.original_language">
                            
                                {{movie.original_language}}
                            </li>
                            <li v-if="movie.vote_average!=0" class="secondary">
                                <strong>voto: </strong> 
                                <star-rating
                                    :star-size=15
                                    :read-only=true
                                    :rating="Math.ceil(movie.vote_average/2)"
                                    :show-rating="false"
                                    inactive-color="000"
                                    border-width="2"
                                    border-color="#ffd055"
                                    active-color="#ffd055"
                                    padding=0
                                    glow=8
                                    glow-color="#ffd055"
                                    inline=true
                                    />
                            </li>
                            <li v-if="movie.vote_average==0" class="secondary">
                                <small>Ancora nessun voto</small>
                            </li>
                        </ul>
                    </p>
                  </div>
                </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
    name: "MoviesCard",
    components:{
    StarRating
  },
    props: {
        movies: Array
    },
    data() {
        return {
            flags: ["al", "ar", "bg", "by", "ch", "cn", "cs", "cy", "cz", "da", "de", "ee", "en", "es", "fi", "fr", "gr", "hn", "hr", "in", "is", "it", "ja", "ko", "lt", "lv", "nb", "nl", "no", "pl", "pt", "ro", "ru", "si", "sk", "sq", "sv", "th", "tl", "tr", "ua", "zh"]
        }
    }
}
</script>
