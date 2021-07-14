<template>
  <section>
        <h2>Serie TV</h2>
        
        <ul v-for="(serie, i) in series" :key="i">
            <li class="primary"> 
              
              <h3>{{serie.name}}</h3>

              <ul>
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
                      <span>Lingua originale:</span>
                  </li>
                  <li v-if="serie.vote_average!=0" class="secondary">
                      <span>voto: </span> {{serie.vote_average}}
                  </li>
                  <li v-if="serie.vote_average==0" class="secondary">
                      <small>voto non disponibile </small>
                  </li>
              </ul>

          </li>
        </ul>
  </section>
</template>

<script>
export default {
    name: "Card",
    props: {
        series: Array
    }
}
</script>

<style>

</style>