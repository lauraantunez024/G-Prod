<template>
    <div class="container">
        <!-- <h1> im the directory!!!!!!!!! </h1> -->
        <DirectoryItems/>
    </div>
</template>

<script>

import DirectoryItems from '../components/DirectoryItems.vue'

    export default {
        name: 'DirectoryView',
        components: 
        DirectoryItems
    }
</script>

<style scoped>
h1 {
    color: black;
    font-size: 3rem;
    top: 50%;
    position: absolute;
}



</style>