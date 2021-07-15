<template>
  <main>

        <div>
            <MoviesCard :movies="movieList"/>
        </div>

        <div>
            <SeriesCard :series="seriesList"/>
        </div>
        
        
  </main>
</template>

<script>
import MoviesCard from "./MoviesCard.vue"
import SeriesCard from "./SeriesCard.vue"

export default {
    name: "Main",
    components: {
    MoviesCard,
    SeriesCard
  },
    props: {
        movieList: Array,
        seriesList: Array
    }
}
</script>

<style lang="scss">

@import "./../styles/vars.scss";

h2 {
    color: $netflixDarkRed;
    text-transform: uppercase;
    text-align: center;
    padding: 30px 0;
}

ul {
    width: 90%;
    margin:auto;
    list-style-type: none;
}
img.flag{
    max-height: 1.5rem;
    border: .2px solid gray;
    border-radius: 4px;
    transition: 200ms;

    &:hover {
        transform: scale(1.2);
    }
}

.card{
    overflow-y: auto ;
    min-height: 500px;
    background-color: black;

    h3 {
        color: $netflixRed;
    }
    
    li {
        font-size: 1.5rem;
        padding: 10px;

        &:last-of-type {
            padding-bottom: 50px;
        }

        & strong {
            color: $netflixRed;
        }
    }
}

.hover-txt {
    display: none;
}

.hover-here:hover {
    cursor:pointer;

    & img:not(.flag){
        filter:brightness(0);
    }

    & .hover-txt {
        display: inline;
    }
}
</style>