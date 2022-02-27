<template>
    <div >
        <h1>Lista Film</h1>
        <section v-for="(film, index) in listaFilmProps" :key="index">
            <ul>
                <img :src="`https://image.tmdb.org/t/p/w45/${film.poster_path}`" alt="">
                <li>Titolo: {{film.title}}</li>
                <li>Titolo originale: {{film.original_title}}</li>
                <li>Lingua originale: <lang-flag :iso="film.original_language" /></li><br>
                <!-- <li>Voto: <i class="fa-solid fa-star"  v-for="(number, index) in votiInteriProps" :key="index"></i></li><br> -->
            </ul>
        </section>
        <br>
        <h1>Lista Serie Tv</h1>
        <section v-for="(serie) in listaSerieProps" :key="serie.id">
            <ul>
                <img :src="`https://image.tmdb.org/t/p/w45/${serie.poster_path}`" alt="">
                <li>Titolo: {{serie.name}}</li>
                <li>Titolo originale: {{serie.original_name}}</li>
                <li>Lingua originale: <lang-flag :iso="serie.original_language" /></li>
                <li>Voto: <i class="fa-solid fa-star"></i></li><br>
            </ul>
        </section>
    </div>
</template>

<script>
export default {
    name: 'MyMain',
    props: ['listaFilmProps',
            'listaSerieProps',
            'votiInteriProps',
            ] ,
    
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