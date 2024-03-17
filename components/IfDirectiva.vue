<template>
    <h1>Directiva IF - Vue</h1>
    <p v-show="edad < 18">Eres menor de edad</p>
    <p v-show="edad > 18">Eres mayor de edad</p>

</template>


<script lang="ts" setup> 
    let edad = 10;

</script>


<style scope>



</style>