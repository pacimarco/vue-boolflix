<template>
    
    <li>
      <img :src="'https://image.tmdb.org/t/p/w185' + item.poster_path" :alt="'image' + (item.title || item.name)"/>
      
      
        {{item.title || item.name}}
        {{item.original_title || item.original_name}}
        <img v-if="idFlags.includes(item.original_language)"
         :src="require('../assets/images/' + item.original_language + '.png')"/>
         <span v-else>{{item.original_language}}</span>
        
        <!--<li><span>Overview: </span> {{item.overview || item.overview}}</li> -->
        <div>
          <i v-for="n in 5" class="fa-star" :class="(n>starVote(item.vote_average))?'fa-regular':'fa-solid'" :key="n"></i>
        </div>
    </li>    
    
</template>

<script>
export default {
name:"MyCard",
props:{
    item:Object
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

<style>

</style>