<template>
    <h3>{{ counter }}</h3>
    <button @click="addCounter">Incrementar</button>
</template>

<script lang="ts">
    import {ref, Ref } from "vue";
    let counter:Ref = ref(0);
    const addCounter=():void =>{
            counter.value++
    }    
    
</script>


<!--Sin la propiedad source, pero con Composite -->
<!--<script lang="ts">
    /*import { defineComponent, ref, Ref } from "vue";
    export default defineComponent({
        name: 'CounterComposition',
        setup(){
            let counter:Ref = ref(0);
            const addCounter=():void =>{
                counter.value++
            }
            return {counter, addCounter}
        }
    })*/
</script>
-->

<style scoped>
</style>