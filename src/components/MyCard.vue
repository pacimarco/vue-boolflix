<template>
  <div class="container-card"> <!--creare card separate film/serie..come inserire img serie e vote serie,,v-else-->
      <div class="poster">
        <img :src="'https://image.tmdb.org/t/p/w185' + film.poster_path" :alt="'image' + film.title"/>
      </div>
      <ul>
        <li><span>title:</span>{{film.title || serie.name}}</li>
        <li><span>original title:</span>{{film.original_title || serie.original_name}}</li>
        <li><span>language:</span><img v-if="idFlags.includes(film.original_language)" :src="require('../assets/images/' + serie.original_language + '.png')" alt=""><span v-else>{{film.original_language}}</span></li>
        <li><span>vote:</span><i v-for="n in 5" class="fa-star" :class="(n>starVote(film.vote_average))?'fa-regular':'fa-solid'" :key="n"></i></li>
        <li><span>Overview: </span> {{film.overview || serie.overview}}</li>
      </ul>
  </div>
</template>

<script>
export default {
name:"MyCard",
props:{
    filmList:Array,
    tvSerieList:Array
},
methods:{
  starVote(defaultVote){
    return Math.ceil(defaultVote / 2);
  }
}
}

</script>

<style>

</style>