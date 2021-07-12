<template>
  <main>
      <ul>
          <li v-for="(e, i) in movies" :key="i" class="primary"> 

              <ul v-if="e.title.toLowerCase().includes(details.toLowerCase())">
                  <li class="primary">
                      {{e.title}}
                  </li>
                  <li class="secondary">
                      Titolo originale: {{e.original_title}}
                  </li>
                  <li class="secondary">
                      Lingua originale: {{e.original_language}}
                  </li>
                  <li class="secondary">
                      voto: {{e.vote_average}}
                  </li>
              </ul>

          </li>
      </ul>
  </main>
</template>

<script>
import axios from "axios";

export default {
    name: "Main",
    props: {
       details: String,
    },
    data() {
        return {
            apiURL: "https://api.themoviedb.org/3/movie/popular?api_key=498d1c8d4b0a878ee9fc00ed9888ae18",
            movies: []
        }
    },
    created() {
        this.getMovie();
    },
    methods: {
        getMovie() {
            axios
                .get(this.apiURL)
                .then (x => {
                    this.movies=(x.data.results);
                })
        }
    }
}
</script>

<style lang="scss">
@import "./../styles/vars.scss";
ul {
    color:white;
    width: 50%;
    margin:auto;
    list-style-type: none;
}

li.primary {
    font-size: 1.8rem;
    color: $netflixRed;
    padding-top:50px
}

li.secondary {
    font-size: 1.3rem;
    padding:20px;
}

</style>