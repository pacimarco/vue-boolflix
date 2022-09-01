<template>
  <div>
    <section class="movie">
      <h3>Film</h3>
      <ul>
        
        <li>info film</li>
        <li v-for="(film,index) in filmList" :key="index">
            {{film.title}} ---
            {{film.original_title}} ---
            <img class="nation" v-if="idFlags.includes(film.original_language)" :src="require('../assets/images/' + film.original_language + '.png')" alt="">
            <span v-else>{{film.original_language}}</span>
            {{film.original_language}} ---
            {{film.vote_average}}

        </li>
                 
    </ul>
    </section>
    <section class="series">
      <h3>Serie Tv</h3>
      <ul>
        
        <li>info Serie Tv</li>
        <li v-for="(serie,index) in tvSerieList" :key="index">
            {{serie.name}} ---
            {{serie.original_name}} ---
            <img class="nation" v-if="idFlags.includes(serie.original_language)" :src="require('../assets/images/' + serie.original_language + '.png')" alt="">
            <span v-else>{{serie.original_language}}</span>
            {{serie.original_language}} ---
            {{serie.vote_average}}

        </li>
                 
    </ul>

    </section>
    
  </div>
</template>

<script>
    
export default {
name:"MyMain",
props:{
    filmList:Array,
    tvSerieList:Array
},
data(){
  return{
    idFlags:['en','it']
  }
}
}    
</script>

<style lang="scss">

  .nation{
    max-width: 35px;
  }

</style>