<template>
        <div class="col-lg-3">
            <div class="flip-card">
                <div class="flip-card-inner">
                    <div class="flip-card-front">
                        <img class="ms-img-fluid" :src="`https://image.tmdb.org/t/p/w342/${filmProps2.poster_path}`" alt="">
                    </div>
                    <div class="flip-card-back">
                        
                        <ul>
                            
                            <li class="text-center fs-3 lh-1 pt-2">{{filmProps2.title}}</li>
                            <li class="text-center pt-3">{{filmProps2.original_title}}</li>
                            <li class="text-center pt-3"><lang-flag :iso="filmProps2.original_language" /></li>
                            <li class="text-center pt-3">Trama</li>
                            <li class="trama">{{filmProps2.overview}}</li>
                            <!-- <li>Voto: <i class="fa-solid fa-star"  v-for="(number, index) in votiInteriProps" :key="index"></i></li><br> -->
                        </ul>
                    </div>
                </div>
            </div>  
        </div>
</template>

<script>
export default {
    name: 'FilmList',
    props: ['filmProps2']
}
</script>

<style scoped lang="scss">
    .ms-background{
        min-height: 400px;
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

 
    .flip-card {
        background-color: transparent;
        width: 100%;
        min-height: 450px;
        perspective: 1000px;
        margin: 12px 0px;

        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.6s;
            transform-style: preserve-3d;
            box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);

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
                width: 100%;
                height: 450px;
            }

            .flip-card-back {
                background-color: black;
                color: white;
                transform: rotateY(180deg);
                width: 100%;
                height: 450px;
                overflow-y: auto;

                ul{
                    padding: 0px 20px;
                    
                    li{
                        list-style: none;
                    }
                    .trama{
                        text-align: justify;
                    }
                }
                
                
            }
        }
    }

    .flip-card:hover .flip-card-inner {
        transform: rotateY(180deg);
    }
</style>