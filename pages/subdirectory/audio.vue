<template>
    <div>   
        <br>
        <br>
        <br>
        <DirectoryItems v-for="(item, i) in audio" :key="i" :title="item.title" :link="item.link" :image="item.image" />
    </div>
</template>

<script>
import DirectoryItems from '~/components/DirectoryItems.vue';
    export default {
        components: DirectoryItems,

        data() {
            return {
                audio: [
                {
                    title: 'Podcasts',
                    link: '/portfolio/audio',
                    image: 'https://picsum.photos/400/300'


                },
                {
                    title: 'Soundscapes',
                    link: '/portfolio/soundscapes',
                    image: 'https://picsum.photos/400/300'
                },

            ]
            }
        },
        computed: {
            path() {
                return this.$route.path.split[1]
            }
        }
        
    }
</script>

<style scoped>

</style>