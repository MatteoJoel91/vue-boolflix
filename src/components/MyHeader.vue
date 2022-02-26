<template>
    <div>
        <input type="text" v-model="cercaFilm"> 
        <button @click="faiRicerca">ricerca</button>
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
    data(){
        return{
            cercaFilm: '',
        }
    },

    methods:{
        faiRicerca(){
            console.log(this.cercaFilm);
            this.$emit('ricerca', this.cercaFilm)
        }
    }
}
</script>

<style>

</style>