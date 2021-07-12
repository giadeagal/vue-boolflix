<template>
  <header>
      <input type="search" 
      name="" 
      id="" 
      v-model="searchModel"
      @keyup.enter="$emit( 'searchEmit', searchModel )">

      <div type="submit" class="btn btn-danger" @click="$emit( 'searchEmit', searchModel )">Cerca</div>
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

input,
.btn {
    float: right;
    height: 40px;
}



</style>