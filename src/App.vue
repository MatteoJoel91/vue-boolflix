<template>
  <div id="app">
    <MyHeader>
 
    </MyHeader>    <h1>cc</h1> 
    <MyMain></MyMain>
    <MyFooter></MyFooter>
    
  </div>
</template>

<script>

const axios = require('axios');

import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'
import MyFooter from './components/MyFooter.vue'

export default {
  name: 'App',

  data(){
    return{
        listaFilm: [],
        cercaFilm: '',
    }
  },

  components: {
    MyHeader,
    MyMain,
    MyFooter,

  },
  
  methods:{
    getFilm(){
      axios.get('https://api.themoviedb.org/3/search/movie?api_key=9cebc562ed1232cc2dd23bfe6f97bc80&query=star-wars&language=it-IT')
        .then((response) => {
            // handle success
            this.listaFilm = response.data.results;
            console.log(response);
            console.log(this.listaFilm);
    })
    .catch(function (error) {
      // handle error
      console.log(error);
    })
    .then(function () {
      // always executed
    });
    }
  },
  created(){
    this.getFilm();
  }
}

</script>

<style lang="scss">
  @import "./assets/style/generale.scss";
  @import "./assets/style/variabili.scss";
</style>
