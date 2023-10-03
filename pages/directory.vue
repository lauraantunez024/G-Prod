<template>
    <div class="container">
        <br>
        <br>
        <br>
        <br>
        <DirectoryItems v-for="(item, i) in items" :key="i" :title="item.title" :link="item.link" :image="item.image"/>
    </div>
</template>

<script>

import DirectoryItems from '../components/DirectoryItems.vue'

export default {
    name: 'DirectoryView',
    components:
        DirectoryItems,
    data() {
        return {
            items: [

                {
                    title: 'Social Media',
                    link: 'portfolio/social-media',
                    image: 'https://picsum.photos/400/300'
                },
                {
                    title: 'Audio',
                    link: '/subdirectory/audio',
                    image: 'https://picsum.photos/400/300'


                },
                {
                    title: 'Visuals',
                    link: '/subdirectory/video',
                    image: 'https://picsum.photos/400/300'

                },

            ],
          
        }
    }
}
</script>

<!-- 
<style scoped>




</style> -->




<!-- <style scoped>
h1 {
    color: black;
    font-size: 3rem;
    top: 50%;
    position: absolute;
}
</style> -->
<!-- <style scoped>
 /* .container {
    width: 100vw;
    height: 80vh;
    margin: auto;    
 } */

 h1, img {
    margin-left: 25px;
 }

 .v-img {
    height: 90%;
    right: -30%;
    bottom: 16%;
    
 }

 .v-card {
    width: 80vw;
    background-color: whitesmoke;
    height: 40vh;
    /* margin-left: 20vw; */
    /* margin-right: 20vw; */
 }

 .v-card-title {
    font-size: 3rem;
    margin-top: 3vh;
    display: inline-block;
    margin-left: 3vw;
    overflow: visible;
 }

 .v-btn {
    bottom: 40%;
    margin-left: 10vw;
 }

 a {
    bottom: 40%;
 }

</style> -->