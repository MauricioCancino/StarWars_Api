<template>
    <div class="main-container">
        <h1>Personajes</h1>
        <button class="btn-buscar" @click="getData">Mostrar Personajes</button>
        <div class="container">
            <button class="btn-personaje" v-for="(personaje,index) in personajes" :key="index" @click="redirect(personaje.url)"> {{personaje.name}}</button>
        </div>
    </div>
</template>

<script>
import axios from "axios"
export default {
    name: 'personajes-name',
    // props: {},
    data: function(){
        return {
            page:1,
            personajes: []
        }
    },
    // computed: {},
    methods: {
        getData(){
            axios.get(`https://swapi.dev/api/people?page=${this.page}`)
            .then (json=>{
                let results = json.data.results
                results.forEach(personaje => {
                    this.personajes.push(personaje)
                });
                this.page++
            })
        }, redirect(url){
    
        let index = ((url).match(/\d+/))[0]
        console.log(index);
        this.$router.push(`/personajes/${index}`)

    },

    }
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>

h1 {
    color: #fffe0e;
}
    .container {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        width: 90%;
        margin: 0 auto;
        gap: 2px;
        background: black;
        color: #fffe0e;
    }
    .btn-personaje{
        background: transparent;
        color: #fffe0e;
        border: 1px solid white;
    }
    
    .main-container {
        text-align: center;
    }
</style>