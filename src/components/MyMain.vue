<template>
  <main>
    <ul>
        <li class="result" v-for="result in results" :key="result.index">
            <div class="title">{{ result.title }}</div>
            <div class="original-title">{{ result.original_title }}</div>
            <div class="language">{{ result.original_language }}</div>
            <div class="vote">{{ result.vote_average }}</div>
        </li>          
    </ul>
  </main>
</template>

<script>
    import axios from 'axios';
export default {
name:'MyMain',


data(){
    return{
        query: "",
        
    }
},

methods: {
        search() {
            axios
            .get("https://api.themoviedb.org/3/search/movie?api_key=92311e9e4318df2bfa2b9bcfe8d9adfe&query=" + this.query)
            .then(response => {
                this.results = (response.data.results);
                console.log(this.results);
            })
        }
    }
}    
</script>

<style>

</style>