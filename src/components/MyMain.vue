<template>
    <div class="container text-white ms-background">
        
            <div class="row test">
                <h1>LISTA FILM</h1>
                <div class="col-lg-3" v-for="(film, index) in listaFilmProps" :key="index">
                    <div class="flip-card">
                        <div class="flip-card-inner">
                            <div class="flip-card-front">
                                <img class="img-fluid test" :src="`https://image.tmdb.org/t/p/w342/${film.poster_path}`" alt="">
                            </div>
                            <div class="flip-card-back">
                                <ul>
                                    <li>Titolo: {{film.title}}</li>
                                    <li>Titolo originale: {{film.original_title}}</li>
                                    <li>Lingua originale: <lang-flag :iso="film.original_language" /></li><br>
                                    <!-- <li>Voto: <i class="fa-solid fa-star"  v-for="(number, index) in votiInteriProps" :key="index"></i></li><br> -->
                                </ul>
                            </div>
                        </div>
                    </div>  
                </div>
            </div>

        <br>

        
        <div class="row justify-content-center">
            <h1>LISTA SERIE TV</h1>
            <div class="col-lg-3" v-for="(serie) in listaSerieProps" :key="serie.id">
                <div class="ms-container-cards">
                    <img class="ms-img-fluid" :src="`https://image.tmdb.org/t/p/w342/${serie.poster_path}`" alt="">
                </div>
                
                <div class="ms-container-cards ms-none">
                    <ul>
                        <li>Titolo: {{serie.name}}</li>
                        <li>Titolo originale: {{serie.original_name}}</li>
                        <li>Lingua originale: <lang-flag :iso="serie.original_language" /></li>
                        <li>Voto: <i class="fa-solid fa-star"></i></li><br>
                    </ul>
                </div>
                
            </div>
        </div>
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

<style scoped lang="scss">
    .ms-background{
        background-color: #141414;
        h1{
            font-size: 60px;
        }
        .ms-img-fluid{
            width: 100%;
            height: 450px;
            cursor: pointer;
        }
    }

    .test{
        margin: 20px;
    }
    .flip-card {
        background-color: transparent;
        width: 300px;
        height: 300px;
        perspective: 1000px;
    }

    .flip-card-inner {
        position: relative;
        width: 100%;
        height: 100%;
        text-align: center;
        transition: transform 0.6s;
        transform-style: preserve-3d;
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
    }

    .flip-card:hover .flip-card-inner {
        transform: rotateY(180deg);
    }

    .flip-card-front, .flip-card-back {
        position: absolute;
        width: 100%;
        height: 100%;
        -webkit-backface-visibility: hidden;
        backface-visibility: hidden;
    }

    .flip-card-front {
        background-color: #bbb;
        color: black;
    }

    .flip-card-back {
        background-color: black;
        color: white;
        transform: rotateY(180deg);
    }
</style>