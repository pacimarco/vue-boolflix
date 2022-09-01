<template>
  <div id="app">
    <MyHeader @search="searching"/>
    <MyMain :filmList="filmList" :tvSerieList="tvSerieList"/>
  </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import MyMain from './components/MyMain.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    MyHeader,
    MyMain
  },
  data(){
    return{
      filmList:[],
      apiUrl:'https://api.themoviedb.org/3',
      apiKey:'92311e9e4318df2bfa2b9bcfe8d9adfe',
      language: 'it-It',
      tvSerieList:[]

    }
  },
  methods:{
    searching(searchedText){

      const paramsObject = {
        
        params:{
          api_key: this.apiKey,
          language: this.language,
          query: searchedText,
        }
      };
      this.searchedMovies(paramsObject);
      this.searchedSeries(paramsObject);
    },
      searchedMovies(paramsObject){
      axios.get(this.apiUrl + '/search/movie', paramsObject)
      .then(res=>{
        this.filmList = res.data.results;
      });
    },

    searchedSeries(paramsObject){
      axios.get(this.apiUrl + '/search/tv', paramsObject)
      
      .then(res=>{
        this.tvSerieList = res.data.results;
      });
    }
 }
}
</script>

<style lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.css';
</style>
