<template>
    <div class="container">
        <div class="content">
            <div class="title-container">

                <h1 id="title"> Videos</h1>
            </div>
            <v-slide-group show-arrows>
                <v-slide-group-item v-for="(video, i) in videos" :key="i" v-slot="{ isSelected, toggle }">
                    <v-card class="ma-2" rounded :color="isSelected ? 'primary' : undefined" @click="toggle">
                        <!-- <v-card-title> {{ video.name }} </v-card-title> -->
                        <iframe width="100%" height="100%" :src="video.path" title="YouTube video player" frameborder="0"
                            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                            allowfullscreen></iframe>


                    </v-card>
                </v-slide-group-item>

            </v-slide-group>
            <br>
            <div class="title-container">

                <h1> In the Wild Podcast Series</h1>
            </div>
            <v-slide-group show-arrows>
                <v-slide-group-item v-for="(vid, i) in inTheWild" :key="i" v-slot="{ isSelected, toggle }">
                    <v-card class="ma-2" rounded :color="isSelected ? 'primary' : undefined" @click="toggle">
                        <!-- <v-card-title> {{ video.name }} </v-card-title> -->
                        <iframe style="border-radius:12px"
                            :src="vid.path"
                            width="100%" height="352" frameBorder="0" allowfullscreen=""
                            allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
                            loading="lazy"></iframe>
                    </v-card>
                </v-slide-group-item>

            </v-slide-group>
            <br>
           
            <!-- <button class="btn-prev btn" @click="changeVideo('prev')">
                <v-icon>mdi-chevron-double-right</v-icon>
            
            </button>
            <div class="video-container">
         
                <iframe width="560" height="315" src="https://www.youtube.com/embed/ON4du7Zr8pE?si=7COxQnzAZdGOhReE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
            </div>
            <span id="caption">
                <p> {{ currentCaption }}</p>
            </span>

            <button class="btn-next btn" @click="changeVideo('next')"> 
            <v-icon>mdi-chevron-double-right</v-icon>
            </button>  -->

        </div>




    </div>
</template>

<script>

// import '../assets/sass/style.scss'


export default {
    name: 'VideoView',

    data() {
        return {
            videos: [
                {
                    name: '8-Bit Video Game Car Ambient Background',
                    path: 'https://www.youtube.com/embed/bsGPrvOZF1s?si=XQmRISb4uYN5O5gt',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: 'Birthdays - Anti-Smoking PSA',
                    path: 'https://www.youtube.com/embed/ON4du7Zr8pE?si=50h7u1Y2g2VZgWel',
                    caption: "A student production by Grace Rolfe, 'Birthdays' is a Silver Telly Award winning PSA created for Georgia Cancer Center to spread awareness about the dangers of smoking.",
                    titleImage: '',
                    style: ''
                },
                {
                    name: 'Kinetic Type Lyric Video - Running Out of Time by Paramore',
                    path: 'https://www.youtube.com/embed/KkCEPqUVOqI?si=bXzFs8FYpyBbW7Er',
                    caption: 'Paramore lyric video',
                    titleImage: '',
                    style: ''
                },
                {
                    name: 'This Circle - Mixed Media Experimental Stop Motion Short Film',
                    path: 'https://www.youtube.com/embed/L0Dxzw-03Ug?si=GcC3MXwah3u115pG',
                    caption: 'Second Video RAAAAAAAAH',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Augusta University Department of Art & Design's BFA in Digital & Visual Storytelling - Show Reel",
                    path: 'https://www.youtube.com/embed/nFuMaFBuJKc?si=AV-ThOJIqYrsNq93',
                    caption: 'This is the first video weeeeeee',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "alto pablo - don't question",
                    path: 'https://www.youtube.com/embed/6ukfsEdPqPs?si=mVGzjPv8xl1fk-27',
                    caption: 'Second Video RAAAAAAAAH',
                    titleImage: '',
                    style: ''
                },

            ],
            inTheWild: [
                {
                    name: 'From Pages to Platforms: JagPulse launch & Freeze Frame unveiling | In the Wild',
                    path: 'https://www.youtube.com/embed/-TwA8wmlDOY?si=YEpgPTqjfVZB06v_',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Don't miss out on FREE parking this semester | In the Wild",
                    path: 'https://www.youtube.com/embed/a_sZsD_4_6w?si=_bu_2sE564V-JXV8',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Do Black fraternities and sororities live up to their legacy? | In the Wild",
                    path: 'https://www.youtube.com/embed/n0Vd5FnIjYk?si=lYBm_QebVi_NQi8d',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Dating 1101 with Homecoming Royals | In the Wild",
                    path: 'https://www.youtube.com/embed/kmZWV2cBV8s?si=YbCQ3QehC-__kJ2g',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Unraveling medical mistrust and empowering healthcare relationships | In the Wild",
                    path: 'https://www.youtube.com/embed/rLKKAAe-m3E?si=hnnUSnGrU8Y22EAu',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Getting fresh perspectives from Latria Graham & INNOVATE 2023 winners | In the Wild",
                    path: 'https://www.youtube.com/embed/9OZ24t-On-4?si=evP5k-TRa38PQeO_',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Empowering Change: A closer look at Sexual Assault Awareness Month and beyond | In the Wild",
                    path: 'https://www.youtube.com/embed/1Kea4CqN4bE?si=fnM1Fr0yEjwNZi_T',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Voices of Augusta University: Commencement speakers share their stories | In the Wild",
                    path: 'https://www.youtube.com/embed/wvzgX8elup4?si=2i7RukWqbDPFpKsR',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Diamond sports are back in full swing | In the Wild",
                    path: 'https://www.youtube.com/embed/gZpcafqFpFY?si=MEOn7vUn4WB8h5og',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "A conversation with women in cybersecurity and healthcare | In the Wild",
                    path: 'https://www.youtube.com/embed/p1OuqW_3a7E?si=hOX4w2r39k2eYYBx',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "What should you be doing within your career? | In the Wild",
                    path: 'https://www.youtube.com/embed/qAzb9WgX9vI?si=WYvx29AdS0X_30tG',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "It's time to go outside | In the Wild",
                    path: 'https://www.youtube.com/embed/c5A-TuwxMyE?si=-p2fZXlycacuuN5h',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Behind the scenes of MCG's Match Day 2023 | In the Wild",
                    path: 'https://www.youtube.com/embed/r8qH2F9GXgA?si=Kz_cGRzl3xm1wcSu',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Why give to Augusta University? | In the Wild",
                    path: 'https://www.youtube.com/embed/9W0MOLLgx1A?si=nswWre2s6b9-07hI',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },
                {
                    name: "Enhancing mental health and embracing Black History Month | In the Wild",
                    path: 'https://www.youtube.com/embed/WFuMylMccOI?si=XGel9v6CBYz872RI',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                },

            ],
            podcasts: [
                {
                    name: "Welcome back to campus",
                    path: 'https://open.spotify.com/embed/episode/4pdw2uKPJ9AzuPA04YILGX?utm_source=generator',
                    caption: 'After effects project',
                    titleImage: '',
                    style: ''
                }
            ],
            currentSlideIndex: 0


        }
    },

    methods: {
        changeVideo(action) {
            if (action === 'prev') {

                this.currentSlideIndex = (this.currentSlideIndex - 1 + this.videos.length) % this.videos.length
            } else if (action === 'next') {

                this.currentSlideIndex = (this.currentSlideIndex + 1) % this.videos.length
            }
        },

    },
    computed: {
        currentVideo() {
            return this.videos[this.currentSlideIndex].path;
        },

        currentTitle() {
            return this.videos[this.currentSlideIndex].name;
        },
        currentCaption() {
            return this.videos[this.currentSlideIndex].caption;
        },
        currentTitleImage() {
            return this.videos[this.currentSlideIndex].titleImage;
        },


    },



}
</script>

<style scoped> /* .container {

     display: grid;
     grid-template-rows: repeat(5, 1fr);
     grid-template-columns: repeat(5, 1fr);
     width: 100vw;
     height: 100vh;
 }

 .content {
     grid-row-start: 2;
     grid-row-end: 6;
     display: grid;
     grid-template-columns: 10% 70% 10% 10%;
     grid-template-rows: repeat(5, 1fr);
     width: 100vw;
     height: 80vh;
 }

 .video-container {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: 5;
    display: flex;
    justify-content: center;
 } */

 .title-container {
     grid-row-start: 1;
     grid-row-end: 2;
     grid-column-start: 2;
     grid-column-end: 3;
     text-align: center;
     margin: auto;
 }

 h1 {
     font-size: 3.5vw;
     margin-top: 15px;
 }

 video {
     height: 100%;
 }

 .btn {
     height: 5vh;
     width: 6vw;
     margin: auto;
     font-size: 2vw;
     top: 50%;
 }



 button:hover {
     background-color: bisque;


 }

 .v-card {
     height: 30vh;
     width: 30vw;
 }

 .btn-prev {
     /* grid-row-start: 3;
    grid-row-end: 4;
    grid-column-start: 2;
    grid-column-end: 3; */
     position: absolute;
     left: 10%;

 }

 .btn-next {
     /* grid-row-start: 3;
    grid-row-end: 4;
    grid-column-start: 4;
    grid-column-end: 5; */
     position: absolute;
     right: 10%;

 }

 #title {
     margin-top: 10vh;
 }

 #caption {
     grid-row-start: 5;
     grid-row-end: 6;
     grid-column-start: 2;
     grid-column-end: 3;
     text-align: center;
     margin: auto;
     font-size: 1.5vw;
 }</style>
