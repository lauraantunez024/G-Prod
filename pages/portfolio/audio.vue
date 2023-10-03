<template>
    <div class="container">
        <div class="title-container">
            <h1> Podcasts </h1>
        </div>
     
        <br>
        <!-- <div class="episodes">
            <button class="episode" data-spotify-id="spotify:episode:7nrMI0kY9FzXWOCY8ld7KO">
                QJ | Say goodbye to books in the Jag store
            </button>
            <button class="episode" data-spotify-id="spotify:episode:7pw4WvRlsYNRO12thSckUZ">
                Can hispanic students thrive at AU?
            </button>
            <button class="episode" data-spotify-id="spotify:episode:6Bra8Wwa0o0b8KzcNrwH1U">
                Season 4 is the wildest we've ever been
            </button>
        </div> -->

        <div id="embed-iframe"></div>
        <br>
        <v-slide-group show-arrows>
            <v-slide-group-item v-for="(podcast, i) in podcasts" :key="i" v-slot="{ isSelected, toggle }">
                <v-btn class="ma-2 episode" rounded :color="isSelected ? 'primary' : undefined" @click="toggle" :data-spotify-id="podcast.path">
                    {{ podcast.name }}
                </v-btn>
            </v-slide-group-item>

        </v-slide-group>


        <!-- <div class="content">
            <div class="title-container">
                <span class="title-text">
                    <h2 :style="currentData.titleStyle"> {{ currentData.title }} </h2>

                </span>

            </div>

            <div class="desc-container">
                <p>
                    {{ currentData.description }}
                </p>
            </div>

            <div class="photo-container">
                <img v-if="currentData.type === 'Podcasts'" src="../assets/podcast-thumbnail.png" />
                <img v-if="currentData.type === 'Soundscapes'" src="../assets/cover-to-cover.png" />
            </div>
            <div class="audio-container">

                <audio :src="currentData.path" type="audio/mpeg" controls>
                    Your browser not cool enough for this audio file :(
                </audio>
            </div>

            <div class="button-area">
                <div v-if="currentData.type !== 'Podcasts'" class="soundscape-buttons">
                    <button v-if="currentData.name !== 'This is How You Lose the Time War'" id="time-war"
                        @click="chooseData('time-war')"> Time War
                    </button>
                    <button v-if="currentData.name !== 'We Are Okay'" id="we-are-okay" @click="chooseData('we-are-okay')">
                        We Are Okay </button>
                    <button v-if="currentData.type !== 'Podcasts'" @click="chooseData('cowboy-bebop')">Podcasts</button>


                </div>
                <div v-if="currentData.type !== 'Soundscapes'" class="podcast-buttons">
                    <button id="cowboy-bebop" v-if="currentData.name !== 'Cowboy Bebop'"
                        @click="chooseData('cowboy-bebop')">Cowboy Bebop</button>
                    <button v-if="currentData.type !== 'Soundscapes'"
                        @click="chooseData('we-are-okay')">Soundscapes</button>

                    <button id="sweet-thing" v-if="currentData.name !== 'Sweet Thing'"
                        @click="chooseData('sweet-thing')">Sweet Thing</button>
                    <button id="spencer" v-if="currentData.name !== 'Spencer'"
                        @click="chooseData('spencer')">Spencer</button>

                </div>
            </div>
        </div> -->

    </div>
</template>

<script>
import cowboy from '../assets/Cowboy_Bebop.svg.png'
import spencerAudio from '../assets/spencer-audio.mp3'
import spencer from '../assets/Spencer_(film)_Logo.png'
import sweetThing from '../assets/sweet_thing_temp.png'
import '../assets/sass/style.scss'
import cowboyAudio from '../assets/cowboy-bebop-podcast.mp3'
import sweetThingAudio from '../assets/sweet-thing-audio.mp3'
import ninaHeader from '../assets/ninaLacour.png'
import ninaAudio from '../assets/nina-audio.mp3'
import timewarAudio from '../assets/timewar-audio.mp3'
import timeWarHeader from '../assets/time-war-header.jpeg'



export default {
    name: 'AudioView',
    mounted() {
        let spotify = document.createElement('script')
        let script = document.createElement('script')
        spotify.setAttribute('src', 'https://open.spotify.com/embed-podcast/iframe-api/v1')
        script.setAttribute('type', 'text/javascript')
        window.onSpotifyIframeApiReady = (IFrameAPI) => {
            const element = document.getElementById('embed-iframe');
            const options = {
                uri: 'spotify:episode:4pdw2uKPJ9AzuPA04YILGX'
            };
            const callback = (EmbedController) => {
                document.querySelectorAll('.episode').forEach(
                    episode => {
                        episode.addEventListener('click', () => {
                            EmbedController.loadUri(episode.dataset.spotifyId)
                        });
                    })
            };

            IFrameAPI.createController(element, options, callback);
        };
        document.head.appendChild(spotify)
        document.head.appendChild(script)
    },
    data() {
        return {
            // currentData:
            // {
            //     name: 'Cowboy Bebop',
            //     title: "COWBOY BEBOP FT. KAYLAN | AUG MEDIA PRODUCTION CLUB PODCAST EP.2",
            //     type: 'Podcasts',
            //     titleStyle: "font-family: 'Cheltenham Condensed'; font-size: 1.75rem;",
            //     description: "Grace and guest Kaylan talk about Cowboy Bebop's lasting legacy in preparation for Netflix's live action spin on the show.",
            //     path: cowboyAudio,
            //     titleImage: cowboy,
            // },
            podcasts: [
                {
                    name: 'QJ | Say goodbye to books in the Jag store',
                    path: 'spotify:episode:7nrMI0kY9FzXWOCY8ld7KO',
                    caption: 'After effects project',
                    
                },
                {
                    name: 'Welcome back to campus (with the Rices)',
                    path: 'spotify:episode:4pdw2uKPJ9AzuPA04YILGX',
                    caption: 'After effects project',
                    
                },
                {
                    name: "Season 4 is the wildest we've ever been",
                    path: 'spotify:episode:6Bra8Wwa0o0b8KzcNrwH1U',
                    caption: 'After effects project',
                    
                },
                {
                    name: 'Can hispanic students thrive at AU?',
                    path: 'spotify:episode:7pw4WvRlsYNRO12thSckUZ',
                    caption: 'After effects project',
                    
                },
                {
                    name: 'QJ | Building a life skills toolbox for college students',
                    path: 'spotify:episode:5hKMeceki3zfFHpwnEwQW4',
                    caption: 'After effects project',
                    
                },
                {
                    name: 'How healthy is Georgia?',
                    path: 'spotify:episode:1j4puBVlEoCPV9RDzpNfE4',
                    caption: 'After effects project',
                },
                {
                    name: "QJ | Let's get digital ... AU online is coming",
                    path: 'spotify:episode:5ekndojtktPb2WHDLLbGFl',
                    caption: 'After effects project',
                },
                {
                    name: "Don't be a refund check baller" ,
                    path: 'spotify:episode:1j4puBVlEoCPV9RDzpNfE4',
                    caption: 'After effects project',
                },
                {
                    name: "Augusta Volleyball has eyes set on Nationals" ,
                    path: 'spotify:episode:3jC2HvtcRdpN7uys0rl5SO',
                    caption: 'After effects project',
                },
                {
                    name: "Time for harvesting and building up the community" ,
                    path: 'spotify:episode:4OXhyOL2e4Cc9F5pdMf4JF',
                    caption: 'After effects project',
                },
                {
                    name: "The new Mr. & Miss AU are here" ,
                    path: 'spotify:episode:6XOkKImzARpDV3Rjf8F1QE',
                    caption: 'After effects project',
                },
                {
                    name: "What are you doing this fall?" ,
                    path: 'spotify:episode:1IAmFXpE7pMJD7PIvA4dtJ',
                    caption: 'After effects project',
                },
                {
                    name: "The Georgia Cyber Center is ready for SIEGE" ,
                    path: 'spotify:episode:4Bono9KqyA8fzfmSqTJWlr',
                    caption: 'After effects project',
                },
                {
                    name: "Where have we been?" ,
                    path: 'spotify:episode:2Eh2Z2stlUQYvah0seNwNr',
                    caption: 'After effects project',
                },
                {
                    name: "Who are you celebrating for Graduation?" ,
                    path: 'spotify:episode:6ozFEorzki3XUl2e0fEVQT',
                    caption: 'After effects project',
                },
                {
                    name: "100th episode" ,
                    path: 'spotify:episode:60E1uU9c0JxQOgCEqShdms',
                    caption: 'After effects project',
                },
                {
                    name: "From pages to platforms" ,
                    path: 'spotify:episode:2RPj4wFSVwt1WgFTkyFT8B',
                    caption: 'After effects project',
                },
                {
                    name: "Dating 1101 with Homecoming Royals" ,
                    path: 'spotify:episode:2XxtOhiKiBK9QcqSrzGCix',
                    caption: 'After effects project',
                },
                {
                    name: "From pages to platforms" ,
                    path: 'spotify:episode:2RPj4wFSVwt1WgFTkyFT8B',
                    caption: 'After effects project',
                },
                {
                    name: "Don't miss out on free parking this semester" ,
                    path: 'spotify:episode:0MKMyxaMVZQt8SQHhXCIRr',
                    caption: 'After effects project',
                },
                {
                    name: "Enhancing Mental Health and embracing Black History Month" ,
                    path: 'spotify:episode:6wJ8ZTQjGFinYwjgzIGDgo',
                    caption: 'After effects project',
                },
                {
                    name: "Women in Cyber Security and HealthCare" ,
                    path: 'spotify:episode:49gRuuezcLPzKswsRmH3My',
                    caption: 'After effects project',
                },
                {
                    name: "Black fraternities and sororities" ,
                    path: 'spotify:episode:12ZoyU5g43RH2YmtCGCKjc',
                    caption: 'After effects project',
                },
                {
                    name: "Why give to AU?" ,
                    path: 'spotify:episode:1EmozSulqpkiU8yQaPxvBv',
                    caption: 'After effects project',
                },
                {
                    name: "BTS MCG's Matchday 2023" ,
                    path: 'spotify:episode:1Fi1ctLgJIaK3QTJUwgUs0',
                    caption: 'After effects project',
                },
                {
                    name: "Empowering Change" ,
                    path: 'spotify:episode:7hPPTAeZtml3CLKZZdw3bp',
                    caption: 'After effects project',
                },
                {
                    name: "Voices of Augusta University" ,
                    path: 'spotify:episode:5aSs4lrksGVnqljp01eOPb',
                    caption: 'After effects project',
                },
                {
                    name: "What should you be doing within your career" ,
                    path: 'spotify:episode:0YP2uI8poSBrWlNnb81Ma0',
                    caption: 'After effects project',
                },
                {
                    name: "Fresh Perspectives from 2023 Innovate winners" ,
                    path: 'spotify:episode:1FS4TikOUCObDgqXyZmlZY',
                    caption: 'After effects project',
                },
                {
                    name: "It's time to go outside" ,
                    path: 'spotify:episode:1PToYI4Xi0oPewsAfa48mx',
                    caption: 'After effects project',
                },

            ],


        }
    },
    methods: {
        chooseData(name) {
            if (name === 'sweet-thing') {
                this.currentData = {
                    name: 'Sweet Thing',
                    title: "Alexandre Rockwell's Sweet Thing | AUG Media Production Club Podcast Ep. 3",
                    type: 'Podcasts',
                    titleStyle: "font-family: 'Morgen'; font-size: 1.75rem",
                    description: "Grace and Sarah discuss Alexandre Rockwell's most recent film, Sweet Thing, screening at the AUG Cinema Series at the Maxwell Theatre on 11/18. Mild spoilers may be discussed.",
                    path: sweetThingAudio,
                    titleImage: sweetThing,
                }
            } else if (name === 'cowboy-bebop') {
                this.currentData = {
                    name: 'Cowboy Bebop',
                    title: "COWBOY BEBOP FT. KAYLAN | AUG MEDIA PRODUCTION CLUB PODCAST EP.2",
                    type: 'Podcasts',
                    titleStyle: "font-family: 'Cheltenham Condensed'; font-size: 1.75rem;",
                    description: "Grace and guest Kaylan talk about Cowboy Bebop's lasting legacy in preparation for Netflix's live action spin on the show.",
                    path: cowboyAudio,
                    titleImage: cowboy,

                }
            } else if (name === 'spencer') {
                this.currentData = {
                    name: 'Spencer',
                    title: "Pablo Larrain's Spencer | AUG Media Production Club Podcast Ep. 4",
                    type: 'Podcasts',
                    titleStyle: "font-family: 'Aviano Flare'; font-size: 1.4rem;",
                    description: "Grace and Sarah discuss Alexandre Rockwell's most recent film, Sweet Thing, screening at the AUG Cinema Series at the Maxwell Theatre on 11/18. Mild spoilers may be discussed.",
                    path: spencerAudio,
                    titleImage: spencer,
                }
            } else if (name === 'we-are-okay') {
                this.currentData = {
                    name: 'We Are Okay',
                    title: "Cover to Cover Ep. 1 - WE ARE OKAY by Nina LaCour",
                    type: 'Soundscapes',
                    titleStyle: "font-family: 'Futura'; font-size: 2rem;",
                    description: "Cover to Cover is a soundscape podcast about books. This is a sample episode covering (hehe) We Are Okay by Nina LaCour.",
                    path: ninaAudio,
                    titleImage: ninaHeader,
                }
            } else if (name === 'time-war') {
                this.currentData = {
                    name: 'This is How You Lose the Time War',
                    title: "Cover to Cover Ep. 2 - This is How You Lose the Time War by Amal El-Mohtar and Max Gladstone",
                    type: 'Soundscapes',
                    titleStyle: "font-family: 'Bauer'",
                    description: "Cover to Cover is a soundscape podcast about books. This is a sample episode covering (hehe) This is How You Lose the Time War by Amal El-Mohtar and Max Gladstone.",
                    path: timewarAudio,
                    titleImage: timeWarHeader
                }
            }
        },

    },

}
</script>




<style scoped>
body {
    display: flex;
    gap: 1rem;
}

.episodes {
    display: flex;
    flex-direction: column;
}

.episode {
    min-width: max-content;
    margin-bottom: .8rem;
    padding: .8rem 1rem;
    border-radius: 10px;
    border: 0;
    background: #191414;
    color: #fff;
    cursor: pointer;
}

.episode:hover {
    background: #1Db954;
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

.title-container {
    margin: auto;
    text-align: center;
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
}
</style>

<!-- 
<style scoped>
/* .container {
    display: grid;
    height: 100vh;
    width: 100vw !important;
    grid-template-rows: repeat(5, 1fr);
} */

/* .content {
    display: grid;
    width: 100vw !important;
    grid-row-start: 2;
    grid-row-end: 6;
    grid-template-columns: 1% 45% 5% 40% 9%;
    grid-template-rows: repeat(10, 1fr);
} */

h1 {
    text-align: center;
    font-size: 5rem;
}

.photo-container img {
    height: 100%;
    margin-left: 15%;
}

#sweet-thing {
    margin: auto;
}

button:hover {
    background-color: cadetblue;
}

.title-text {
    -webkit-transform: skew(50deg);
    margin-bottom: 15px;
    transform: skew(50deg);
    justify-content: center;

}

/* .title-container h2 {

    max-height: 100%;
    display: flex;
    transform: skew(50deg);
    -webkit-transform: skew(50deg);
    margin-left: 10%;
    text-align: center;
    font-size: 1.5rem;
    font-family: 'Cheltenham Condensed';
    grid-column-start: 3;
    grid-column-end: 5;

} */

.desc-container p {
    text-align: center;
    margin-top: 10%;
    font-size: 1.5rem;
    /* margin-left: 15px; */
}

.photo-container {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 2;
    grid-row-end: 7;
    /* border: 3px black solid; */
    border-radius: 2%;


}

.podcast-buttons {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 9;
    grid-row-end: 10;
    display: flex;
    flex-wrap: none;
    justify-content: space-between;
    width: 100%;
}

.soundscape-buttons {
    grid-column-start: 2;
    grid-column-end: 3;
    grid-row-start: 9;
    grid-row-end: 10;
    display: flex;
    flex-wrap: none;
    justify-content: space-between;
    width: 100%;
}

.title-container {
    grid-column-start: 3;
    grid-column-end: 5;
    grid-row-start: 2;
    grid-row-end: 4;
    width: 80%;
    height: 65%;
    transform: skew(-50deg);
    background-color: blanchedalmond;
    overflow: hidden;
}


.desc-container {
    grid-row-start: 4;
    grid-row-end: 7;
    grid-column-start: 3;
    grid-column-end: 5;
    /* border: green solid 3px; */

}

.audio-container {
    grid-row-start: 8;
    grid-row-end: 9;
    grid-column-start: 2;
    grid-column-end: 5;
}

audio {
    width: 90%;
    color: red;
    margin-left: 5%;
}

button {
    height: 100%;
    border-radius: 50%;
}

.button-area {
    grid-row-start: 9;
    grid-row-end: 10;
    grid-column-start: 2;
    grid-column-end: 5;
    display: flex;
    align-content: space-between;
    gap: 20px;
    /* justify-self: center; */

}



button {
    background-color: cornflowerblue;
    color: black;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    font-size: 1.5rem;
    margin: auto;
    min-width: 10%;
    max-width: 20%;



}

audio::-webkit-media-controls-panel {
    background-color: gray;
}

audio::-webkit-media-controls-timeline {
    background-color: #B1D4E0;
    border-radius: 25px;
    /* margin-left: 10px; */
    /* margin-right: 10px; */
}
</style> -->