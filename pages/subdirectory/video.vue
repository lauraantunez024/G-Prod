<template>
    <div>   
        <br>
        <br>
        <br>
        <DirectoryItems v-for="(item, i) in video" :key="i" :title="item.title" :link="item.link" :image="item.image" />
    </div>
</template>

<script>
    export default {

        data() {
            return {
            video: [
                {
                    title: 'Videography',
                    link: '/portfolio/videos',
                    image: 'https://picsum.photos/400/300'


                },
                {
                    title: 'Photography',
                    link: '/portfolio/photography',
                    image: 'https://picsum.photos/400/300'
                },

            ],
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