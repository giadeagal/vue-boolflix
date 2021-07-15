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
                            <span>Lingua originale: </span> 

                            <img 
                            v-if="flags.includes(movie.original_language)"

                            :src="
                                require(`../assets/flags/${movie.original_language}.png`)
                            " 
                            :alt="movie.original_language">
                        
                            {{movie.original_language}}
                        </li>
                        <li v-if="movie.vote_average!=0" class="secondary">
                            <span>voto: </span> {{movie.vote_average}}
                        </li>
                        <li v-if="movie.vote_average==0" class="secondary">
                            <small>Ancora nessun voto</small>
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
    },
    data() {
        return {
            flags: ["al", "ar", "bg", "by", "ch", "cn", "cs", "cy", "cz", "da", "de", "ee", "en", "es", "fi", "fr", "gr", "hn", "hr", "in", "is", "it", "ja", "ko", "lt", "lv", "nb", "nl", "no", "pl", "pt", "ro", "ru", "si", "sk", "sq", "sv", "th", "tl", "tr", "ua", "zh"]
        }
    }
}
</script>

