<template>
    <div class="container">
        <div class="label">
            Nombre:
        </div>
        <div class="info">
            {{personaje.name}}
        </div>
        <div class="label">
            Género:
        </div>
        <div class="info">
            {{personaje.gender}}
        </div>
        <div class="label">
            Altura
        </div>
        <div class="info">
            {{personaje.height}}
        </div>
        <div class="label">
            Número peliculas:
        </div>
        <div class="info">
            {{personaje.films.length}}
        </div>
    </div>
</template>

<script>
import axios from "axios"
export default {
    name: 'personaje-name',
    props: {
        id:{ 
            type:String,
            required:true
    },
    },
    data: function(){
        return {
            personaje:{
                name:"",
                gender:"",
                height: "",
                films: [],
            },
        }
    },
    // computed: {
    //     id() {
    //         return this.$route.params.id
    //     }
    // },
    methods: {
        getPersonaje() {
            axios.get(`https://swapi.dev/api/people/${this.id}`)
            .then(result => {
                // console.log(result)
                this.personaje= result.data
            })
        }
    },
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    created() {
        this.getPersonaje()
    }
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    .contaier {
        width: 40%;
        max-width: 25rem;
        margin: 0 auto;
        color: #747474;
        text-align: center;
        border: 2px solid #747474;
    }
    .label {
        background: #747474;
        color: #fffe0e;
        padding: 10px;
    }
    .info {
        color: white;
        padding: 10px;
    }
</style>