<template>
  <div id="app">
    <MyHeader @ricerca='effettuaRicerca' />
    <MyMain :listaFilmProps="listaFilm"/>
      <!-- <input type="text" v-model="cercaFilm"> 
      <button @click="effettuaRicerca">ricerca</button> -->

      <!-- <ul v-for="(film, index) in listaFilm" :key="index">
          <li>Titolo: {{film.title}}</li>
          <li>Titolo originale: {{film.original_title}}</li>
          <li>Lingua originale: {{film.original_language}}</li>
          <li>Voto: {{film.vote_average}}</li><br>
      </ul> -->
     
    <MyFooter />
    
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
        cercaFilm:'',      
        listaFilm: [],       
    }
  },

  components: {
    MyHeader,
    MyMain,
    MyFooter,

  },
  
  methods:{
    getFilm(text){
      axios.get(`https://api.themoviedb.org/3/search/movie?api_key=9cebc562ed1232cc2dd23bfe6f97bc80&query=${text}&language=it-IT`)
        .then((response) => {
            // handle success
            this.listaFilm = response.data.results;
            console.log(response);
            console.log(this.listaFilm);
      })
    },

    effettuaRicerca(valore) {
      this.cercaFilm = valore;
      this.getFilm(this.cercaFilm);
      this.cercaFilm = "";
    },
  },
  // created(){
  //   this.getFilm();
  // }
}

</script>

<style lang="scss">
  @import "./assets/style/generale.scss";
  @import "./assets/style/variabili.scss";
</style>
