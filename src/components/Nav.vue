<template>
    <div>
         <nav>
      <router-link to="/">Home</router-link> |
      <router-link to= "/personajes">Personajes |</router-link>
      <router-link to= "/contacto"> Contactos</router-link>
    </nav>

    </div>
</template>

<script>
export default {
    name: 'nav-name',
    // props: {},
    data: function(){
        return {}
    },
    // computed: {},
    //methods: {}
    // watch: {},
    // components: {},
    // mixins: [],
    // filters: {},
    // -- Lifecycle Methods
    // -- End Lifecycle Methods
}
</script>

<style scoped>
    
    nav {
        background: #fffe0e;
        gap: 10px;
        display: flex;
    }

</style>