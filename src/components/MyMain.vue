<template>
  <div>
    <section class="movie">
      <h3>Film</h3>
      <ul>
        
        <li>info film</li>
        <li v-for="(film,index) in filmList" :key="index">
          <img :src="'https://image.tmdb.org/t/p/w185' + film.poster_path" :alt="'image' + film.title"/>
            {{film.title}} ---
            {{film.original_title}} ---
            <img class="nation" v-if="idFlags.includes(film.original_language)" :src="require('../assets/images/' + film.original_language + '.png')" alt="">
            <span v-else>{{film.original_language}}</span>
            

            <div>
              <i v-for="n in 5" class="fa-star" :class="(n>starVote(film.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
            </div>

        </li>
                 
    </ul>
    </section>
    <section class="series">
      <h3>Serie Tv</h3>
      <ul>
        
        <li>info Serie Tv</li>
        <li v-for="(serie,index) in tvSerieList" :key="index">
          <img :src="'https://image.tmdb.org/t/p/w185' + serie.poster_path" :alt="'image' + serie.name"/>
            {{serie.name}} ---
            {{serie.original_name}} ---
            <img class="nation" v-if="idFlags.includes(serie.original_language)" :src="require('../assets/images/' + serie.original_language + '.png')" alt="">
            <span v-else>{{serie.original_language}}</span>
            

            <div>
              <i v-for="n in 5" class="fa-star" :class="(n>starVote(serie.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
            </div>

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
},
methods:{
  starVote(defaultVote){
    return Math.ceil(defaultVote / 2);
  }
}
}    
</script>

<style lang="scss">

  .nation{
    max-width: 35px;
  }

</style>