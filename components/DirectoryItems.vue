<template>
    <v-container class="container">
        <v-spacer/>
        <v-row>

                    <v-col v-for="(item, i) in items" :key="i" flex>

                        <v-card>
                            <v-card-title> {{ item.title }}</v-card-title>
                            <v-img class="justify-end" :src="item.image" alt="" />

                                <v-btn :to="item.link">View Projects</v-btn>
                                <a :href="item.link">ViewP</a>
                        </v-card>
                    </v-col>
        </v-row>

    </v-container>
</template>

<script>
export default {
    name: 'DirectoryItems',
    data() {
        return {
            items: [

                {
                    title: 'Social Media',
                    link: '/social-media',
                    image: 'https://picsum.photos/400/300'
                },
                {
                    title: 'Audio',
                    link: '/audio',
                    image: 'https://picsum.photos/400/300'
                    

                },
                {
                    title: 'Videography',
                    link: '/videos',
                    image: 'https://picsum.photos/400/300'

                },
                {
                    title: 'Photography',
                    link: '/photography',
                    image: 'https://picsum.photos/400/300'

                },
             
            ],
        }   
    },
}
</script>

<style scoped>
 .container {
    display: grid;
    width: 100vw;
    height: 80vh;
    /* margin-left: 10vw; */
    /* border: black 5px solid; */
    margin: auto;    
 }

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

</style>