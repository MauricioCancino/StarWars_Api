<template>
<div>
    <h1>La página que buscas no existe </h1>
   <router-link to="/">Ir a inicio</router-link>
    </div>
</template>

<script>
export default {
    name: 'NotFound-name',
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
    div {
        text-align: center;
    }
    h1 {
        color: #fffe0e;
    }
</style>