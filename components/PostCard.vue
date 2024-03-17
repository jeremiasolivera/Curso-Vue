<template>
    <div class="post-card">
        <h2>Bienvenido al post</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aspernatur at quod obcaecati molestiae accusamus nesciunt nisi provident earum a nostrum! Voluptatibus molestias facilis sequi dignissimos vitae quo aliquam quibusdam ducimus.</p>
        <PostBtnVue/>
    </div>
</template>



<script lang="ts" setup>
    import PostBtnVue from './PostBtn.vue';
</script>


<style scoped>
.post-card{
    background-color: tomato;
    border: 1px solid red;
    border-radius: 5px;
}
</style>