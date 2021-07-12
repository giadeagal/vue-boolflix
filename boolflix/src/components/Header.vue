<template>
  <header>
      <input type="search" 
      name="" 
      id="" 
      placeholder="Cerca qui" 
      v-model="searchModel" 
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
    display:table;
    clear: both;
}

input {
    float: right;
    margin-right: 200px;
}


</style>