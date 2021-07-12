<template>
  <div id="app">
    <Header @searchEmit="searchFunction"/>
    <Main/>
  </div>
</template>

<script>
import Header from "./components/Header.vue"
import Main from "./components/Main.vue"

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      searchFinal: ""
    }
  },
  methods: {
    searchFunction(searched) {
      this.searchFinal = searched;
    }
  }
}
</script>

<style lang="scss">
@import "@/styles/commons.scss";

body {
  background-color: black;
}

.prova {
  color:white;
}

</style>
