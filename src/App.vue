<template>
  <div id="app">
    <MyHeader></MyHeader>
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
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) => {
            // handle success
            this.listaFilm = response.data.response;
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
  }
}
</script>

<style lang="scss">
  @import "./assets/style/generale.scss";
  @import "./assets/style/variabili.scss";
</style>
