<template>
  <main>
    <ul>
        <li v-for="(film,index) in filmList" :key="index">
            {{film.title}} 
            {{film.original_title}} ---
            {{film.original_language}} --- 
            {{film.vote_average}}
        </li>          
    </ul>
  </main>
</template>

<script>
    
export default {
name:"MyMain",
props:{
    filmList:Array
}
}    
</script>

<style>

</style>