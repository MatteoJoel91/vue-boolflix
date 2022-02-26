<template>
    <div>
        <ul v-for="(film, index) in listaFilmProps" :key="index">
          <li>Titolo: {{film.title}}</li>
          <li>Titolo originale: {{film.original_title}}</li>
          <li>Lingua originale: {{film.original_language}}</li>
          <li>Voto: {{film.vote_average}}</li><br>
      </ul>
    </div>
</template>

<script>
export default {
    name: 'MyMain',
    props: ['listaFilmProps'],
    
    data(){
        return{
            
        }
    },

    methods:{
        
    }
}
</script>

<style>

</style>