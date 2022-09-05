<template>
  <div>
    
    <section class="movie">
      
      <h3>Film</h3>
      <ul>
        
        <li>info film</li>
        <MyCard v-for="(film,index) in filmList" :key="index" :item="film"></MyCard>
                 
      </ul>
    </section>
    <section class="series">
     
      <h3>Serie Tv</h3>
      <ul>
        
        <li>info Serie Tv</li>
        <MyCard v-for="(serie,index) in tvSerieList" :key="index" :item="serie"></MyCard>
        
                 
      </ul>

    </section>
    
  </div>
</template>

<script>
    import MyCard from './MyCard.vue';
export default {
name:"MyMain",
components:{
  MyCard,
},

data(){
  return{
    idFlags:['en','it']
  }
},

}    
</script>

<style lang="scss">

  .nation{
    max-width: 35px;
  }

</style>