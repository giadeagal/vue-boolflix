<template>
  <section>
        <h2>Serie TV</h2>

        <ul v-for="(serie, i) in series" :key="i">
            <li class="primary"> 
              
              <h3>{{serie.name}}</h3>

              <ul>
                  <li class="secondary">
                    <img :src="`
                                https://image.tmdb.org/t/p/w342/${serie.poster_path}
                            `" 
                            alt="">
                 </li>
                  <li class="secondary" v-if="serie.overview != ''">
                      <span>Trama:</span> {{serie.overview}}
                  </li>
                  <li class="secondary" v-if="serie.overview == ''">
                      <small>Trama non disponibile</small>
                  </li>
                  <li class="secondary">
                      <span>Titolo originale:</span> {{serie.original_name}}
                  </li>

                  <li class="secondary">
                    <span>Lingua originale: </span> 

                    <img class="flag"
                        v-if="flags.includes(serie.original_language)"

                        :src="
                            require(`../assets/flags/${serie.original_language}.png`)
                        " 
                        :alt="serie.original_language">
                    
                    {{serie.original_language}}
                  </li>

                  <li v-if="serie.vote_average!=0" class="secondary">
                      <span>voto: </span> {{Math.ceil(serie.vote_average/2)}}
                  </li>
                  <li v-if="serie.vote_average==0" class="secondary">
                      <small>Ancora nessun voto</small>
                  </li>
              </ul>

          </li>
        </ul>
  </section>
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
    name: "Card",
    components: StarRating,
    props: {
        series: Array
    },
    data() {
        return {
            flags: ["al", "ar", "bg", "by", "ch", "cn", "cs", "cy", "cz", "da", "de", "ee", "en", "es", "fi", "fr", "gr", "hn", "hr", "in", "is", "it", "ja", "ko", "lt", "lv", "nb", "nl", "no", "pl", "pt", "ro", "ru", "si", "sk", "sq", "sv", "th", "tl", "tr", "ua", "zh"]
        }
    }
}
</script>

<style>

</style>