<template>
    <div class='app'>
        <!-- <div class="border-container">
            <img class="border-detail" 
                src="src/assets/img/border-detail.png" 
                alt="border detail" 
            />
            <img class="border-detail invert" 
                src="src/assets/img/border-detail.png" 
                alt="border detail" 
            />
        </div> -->
        <video-panel>
                <video
                    class="video-display video" 
                    src="src/assets/video/replay-cross.mp4"
                    autoplay 
                    muted
                    loop   
                    v-on:click="watchToggle"  
                >
                </video>
        </video-panel>
        <div class="colorize"> </div>

        <video-panel-title 
            :name='game.character.name'
            :title='game.description.title'
            :subtitle='game.description.subtitle'
        >
        </video-panel-title>
        <div class='static-bar'>
            <img class='game-logo' 
                :src='game.image.src' 
                :alt='game.image.alt'
            />
        </div>

        <div class="half-panel">
            <character-image>
                <img 
                    :src='game.character.image' 
                    :alt='game.character.description'
                />
            </character-image>
        </div>

        <div class="panel">
            <video-slide>
                <li
                    class="slide-item"
                    v-for="video in game.character.video"
                >
                    <a v-bind:href="video.src">
                        <img :src="video.thumb" />
                    </a>
                </li>
            </video-slide> 
        </div>

    </div>
</template>

<script>
import VideoPanel from './components/shared/VideoPanel/VideoPanel.vue';
import VideoPanelTitle from './components/shared/VideoPanelTitle/VideoPanelTitle.vue';
import CharacterImage from './components/shared/CharacterImage/CharacterImage.vue';
import Slide from './components/shared/Slide/Slide.vue';

export default {
    methods: {
        watchToggle: function(event) {
            let container = document.querySelector('.video-display');
            let video = document.querySelector('.video-display .video');

            if (video.classList.contains('watch')) {
                video.classList.remove('watch')
                container.classList.remove('watch')
            } else {
                video.classList.add('watch')
                container.classList.add('watch')
                video.setAttribute('v-on:click','watchToggle')
            }
        }
    },

    components: {
        'video-panel': VideoPanel,
        'video-panel-title': VideoPanelTitle,
        'character-image': CharacterImage,
        'video-slide': Slide,
    },

    data(){
        return {
            game:{
                description: {
                    title: "TOP 5",
                    subtitle: "BEST COMBOS"
                },

                image:{
                    src: "src/assets/img/brawhalla-logo.png",
                    alt: "Logo do jogo Brawhalla"
                },

                character: {
                    name: 'CROSS',
                    image: "src/assets/img/cross_img1.png",
                    description: 'Imagem do Cross',
                    video:[
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumb/thumb1.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "/src/assets/img/thumb/thumb2.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumb/thumb3.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumb/thumb1.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumb/thumb1.png"
                        }                   
                    ],
                },    
            }
        }
    }
}

</script>

<style>
    * {
        margin: 0px;
        padding:  0px;
        box-sizing: border-box;

    }

    html {

        width: 100vw;
        height: 100vh;
        margin: 0 auto;
        
    }

    body {

        width: 100%;
        height: 100%;
        
        margin: 0 auto;
        
        display: flex;
        justify-content: center;
        align-items: center;
        
        background-color: #182429;
    }

    .app {

        height: 100%;
        width: 100%;
        
        max-width: 1440px;
        max-height: 720px;

        display: flex;

        background-color: #1E1E1E;    
        border-radius: 8px;
        border: 1px solid #193c4b;

    }

    .static-bar {
        z-index: 1;

        display: flex;
        justify-content: center;
        align-items: center;
        
        width: 20%;
        
        background: linear-gradient(180deg, #182429 14.9%, #193C4B 82.08%);
        border-radius: 0px 8px 8px 0px;
    }

    .game-logo {
        min-width: 80%;
        padding: 20px;
    }

    /* .border-container {
        max-width: 1440px;
        width: 100%;
        height: 100%;
        position: absolute;
        z-index: 10;
    }

    .border-detail {
        position: fixed;
        right: 12.5vh;
        top: 50vh;
        mix-blend-mode: color-dodge;
        transform: matrix(0, -1, -1, 0, 0, 0);
    }

    .invert {
        transform: matrix(0, 1, -1, 0, 0, 0);
    } */

    .colorize {
        background: rgba(25, 60, 75, 0.27);
        width: 100%;
        height: 100%;
        position: absolute;
        max-width: 1440px;
        max-height: 720px;
        border-radius: 8px;
    }

    .panel {
        width: 100%;
        height: 100%;
        position: absolute;
        max-width: 1440px;
        max-height: 720px;
        border-radius: 8px;
    }

    .half-panel {
        width: 100%;
        height: 100%;
        position: absolute;
        max-width: 1222px;
        max-height: 720px;
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        border-radius: 8px;
    }

</style>