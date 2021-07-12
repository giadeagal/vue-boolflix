<template>
  <main>
      <ul>
          <li v-for="(e, i) in movies" :key="i" class="primary"> 
              
              {{e.title}}

              <ul>
                  <li class="secondary">
                      {{e.overview}}
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
       
    },
    data() {
        return {
            apiURL: "https://api.themoviedb.org/3/search/movie?api_key=498d1c8d4b0a878ee9fc00ed9888ae18&query=matrix",
            movies: [],
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
                    console.log(this.movies)
                })
        }
    }
}
</script>

<style>

ul {
    color:white
}

li.primary {
    font-size: 1.5rem;
}

li.secondary {
    font-size: .8rem;
}

</style>