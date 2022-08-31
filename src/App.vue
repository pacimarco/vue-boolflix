<template>
  <div id="app">
    <MyHeader @search="searching"/>
    <MyMain :filmList="filmList"/>
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
      language: 'it-It'
    }
  },
  methods:{
    searching(searchedText){
      axios.get(this.apiUrl + '/search/movie?api_key=' + this.apiKey + '&language=' + this.language + '&query=' + searchedText)
      .then(res=>{
        this.filmList = res.data.results;
      })
    }
  }
  
  
}
</script>

<style lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.css';
</style>
