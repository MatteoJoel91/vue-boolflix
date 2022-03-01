<template>
    <div class="ms-container d-flex align-items-center justify-content-between"> 
        <img src="http://www.cartoonmag.it/wp-content/uploads/2017/05/netflix-logo-1024x597.png" alt="">
        <div>
            <input type="text" placeholder="Cerca qualcosa..." v-model="cerca"> 
            <button @click="faiRicerca">RICERCA</button>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
    data(){
        return{
            cerca: '',
        }
    },

    methods:{
        faiRicerca(){
            console.log(this.cerca);
            this.$emit('ricerca', this.cerca)
            this.cerca = '';
        }
    }
}
</script>

<style scoped lang="scss">
    .ms-container{
        width: 100%;
        height: 100px;
        padding: 0 40px 0 40px;
        background-color: #b00707;

        img{
            width: 150px;
        }

        input{
            color: #b00707;
            margin: 5px;
            font-weight: bold;
        }

        button{
            padding: 5px;
            border-radius: 10px;
            color: #b00707;
            background-color: white;
            border: solid 1px #b00707;
            font-weight: bold;
        }
    }
</style>