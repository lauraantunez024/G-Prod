<template>
    <v-container class="container">
        <v-spacer/>
        <v-row>
            <br>
                    <v-col  flex>
                        <v-card>
                            <v-card-title> {{ title }}</v-card-title>
                            <v-img class="justify-end" :src="image" alt="" />

                                <v-btn :to="link">View Projects</v-btn>
                        </v-card>
                    </v-col>
        </v-row>

    </v-container>
</template>

<script>
export default {
    name: 'DirectoryItems',
    props: {
        title: {
            required: true,
            type: String
        },
        link: {
            required: true,
            type: String
        },
        image: {
            required: true,
            type: String
        }
    }
}
</script>

<style scoped>
 .container {
    width: 100vw;
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