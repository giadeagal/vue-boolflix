<template>
  <header>
      <div class="container">
          <div class="logo">
          <a href="#"><h1>Gialloflix</h1></a>
      </div>

      <div class="search">
        <input  type="search" 
                name="" 
                id="" 
                v-model="searchModel"
                placeholder="cerca qui"
                @keyup.enter="$emit( 'searchEmit', searchModel )">
      </div>
      </div>
  </header>
</template>

<script>
export default {
    name: "Header",
    data() {
        return {
            searchModel: ""
        }
    }
}

</script>

<style lang="scss" scoped>
@import "./../styles/vars.scss";

header {
    height: 80px;
    width: 100%;
    background-color: #333;
    padding: 20px;

    & a {
        color: $netflixRed;
        text-decoration: none;
    }
}

.container {
    display: flex;
    justify-content: space-between;
}

</style>