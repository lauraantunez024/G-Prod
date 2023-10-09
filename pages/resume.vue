<template>
    <v-sheet>
        <br>
        <br>
        <br>
        <br>
        <h1 class="text-h1"> Resume </h1>
        <br>
        <v-container>
            <v-sheet class="text-left">
                <h1 class="text-left text-h4"> Social Media Coordinator </h1>
                <h1 class="text-left text-h5"> Who'z Nxt | Pleasanton, CA (Remote) </h1>
                <v-divider :thickness="3"></v-divider>

                <v-list lines="one">
                    <v-list-header class="text-right">
                        Aug 2022 - present
                    </v-list-header>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Use Canva and Adobe Premiere Pro to create graphics and videos for company social media accounts
                    </v-list-item>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Copywriting social media content and captions across Instagram, Facebook, LinkedIn, and Twitter
                    </v-list-item>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Researching industry analytics, competitor accounts, and social media trends to plan content
                        strategy </v-list-item>
                </v-list>

            </v-sheet>
            <br>

            <v-sheet class="text-right">
                <h1 class="text-right text-h4"> Television & Cinema Lab Assistant </h1>
                <h1 class="text-right text-h5"> Augusta University Department of Art & Design | Augusta, GA </h1>
                <v-divider :thickness="3"></v-divider>
                <v-list lines="one">
                    <v-list-header>
                        Feb 2022 - present
                    </v-list-header>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Assisting professors instructing film classes within the lab
                    </v-list-item>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Liasing with faculty and students to schedule equipment and lab facility use
                    </v-list-item>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Aiding video and audio productions within the lab and podcast studio
                    </v-list-item>
                </v-list>
            </v-sheet>



            <br>

            <v-sheet>
                <h1 class="text-left text-h4"> Communications & Marketing Student Assistant </h1>
                <h1 class="text-left text-h5"> Augusta University Division of Communications & Marketing | Augusta, GA </h1>
                <v-divider :thickness="3"></v-divider>

                <v-list lines="one">
                    <v-list-header>
                        May 2022 - May 2023
                    </v-list-header>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Used Adobe Audition to edit weekly 30-minute episodes of Augusta University’s official podcast In
                        The Wild </v-list-item>
                    <v-spacer />
                    <v-list-item class="text-left">
                        <v-icon>mdi-ghost</v-icon>
                        Edited and created promotional videos weekly for Augusta University’s official podcast In The Wild
                        using Adobe Premiere Pro featured on Augusta University’s social media and website
                    </v-list-item>
                    <v-list-item class="text-left">
                        <v-icon>mdi-ghost</v-icon>
                        Managed In the Wild’s social media presence during supervisor’s six-week leave of absence producing
                        engaging content weekly
                    </v-list-item>
                </v-list>
            </v-sheet>
            <br>
            <v-sheet class="text-right">
                <h1 class="text-right text-h4"> Keyholder / Social Media Manager </h1>
                <h1 class="text-right text-h5"> BoxLunch | Augusta, GA </h1>
                <v-divider :thickness="3"></v-divider>

                <v-list lines="one">
                    <v-list-header>
                        Apr 2021 - May 2022
                    </v-list-header>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Oversaw store operations by counting cash drawers, reviewing equipment management, and supervising
                        staff
                    </v-list-item>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Created photo and video content for social media accounts </v-list-item>
                    <v-list-item>
                        <v-icon>mdi-ghost</v-icon>
                        Managed the store social media accounts to increase customer engagement through social media
                    </v-list-item>
                </v-list>
            </v-sheet>
            <br>
            <!-- <v-divider :thickness="5"></v-divider> -->
            <br>
            <h1 class="text-h2">Education </h1>
            <br>
            <h1 class="text-h5"> Bachelor of Fine Arts in Digital and Visual Storytelling
                Augusta University | Augusta, GA Diploma expected December 2023 </h1>




        </v-container>
    </v-sheet>
</template>

<script>
export default {
    name: 'ResumeView'
}
</script>

<style scoped>
h1 {
    text-align: center;
}

#align-right {
    text-align: right !important;
}

.v-container {
    width: 80vw;
}
.v-icon {
    display: inline;
}
</style>