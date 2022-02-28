<template>
    <div class="container text-white ms-background">
        
            <div class="row">
                <h1>LISTA FILM</h1>
                    <FilmList 
                        v-for="(film, index) in listaFilmProps" 
                        :key="index"
                        :filmProps2="film"
                    />     
            </div>

            <br>

            <div class="row">
                <h1>LISTA SERIE TV</h1>
                    <SerieList
                        v-for="(serie, index) in listaSerieProps" 
                        :key="index"
                        :serieProps2="serie"
                    />
            </div>
    </div>
</template>

<script>

    import FilmList from './partials/FilmList.vue'
    import SerieList from './partials/SerieList.vue'

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
    components:{
        FilmList,
        SerieList,
    },

    methods:{
        
    }
}
</script>

<style scoped lang="scss">
   
</style>