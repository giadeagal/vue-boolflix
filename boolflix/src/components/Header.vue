<template>
  <header>

      <input type="search" 
      name="" 
      id="" 
      v-model="searchModel"
      placeholder="cerca qui"
      @keyup.enter="$emit( 'searchEmit', searchModel )">

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

header {
    height: 80px;
    width: 100%;
    background-color: #333;
    padding: 20px;
    content:"";
    position:relative;
}



input {
    position:absolute;
    bottom:20px;
    left:50%;
    transform: translateX(-50%);
}



</style>