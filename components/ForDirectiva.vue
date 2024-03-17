<template>
    <h1>For Directiva - Vue</h1>
    <ul>
        <li v-for="(countrie,index) in countries" :key="index">{{ countrie }}</li>
    </ul>
</template>

<script lang="ts" setup>
    import { Ref, ref } from 'vue'
    let countries:Ref<Array<string>> = ref([
        'Spain',
        'Argentina',
        'Uk',
        'Italy'
    ])





</script>


<style scoped>
</style>