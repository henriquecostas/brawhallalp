<template>
    <div class='app'>
        <video-panel>
        </video-panel>
        <video-panel-title 
            :name='game.character.name'
            :title='game.description.title'
            :subtitle='game.description.subtitle'
        >
        </video-panel-title>
        <div class='static-bar'>
            <img class='game-logo' :src='game.image.src' :alt='game.image.alt'>
        </div>

        <character-image>
            <img 
            :src='game.character.image' 
            :alt='game.character.description'>
            />
        </character-image>
        
    </div>
</template>

<script>
import VideoPanel from './components/shared/VideoPanel/VideoPanel.vue';
import VideoPanelTitle from './components/shared/VideoPanelTitle/VideoPanelTitle.vue';
import CharacterImage from './components/shared/CharacterImage/CharacterImage.vue';

export default {
    components: {
        'video-panel': VideoPanel,
        'video-panel-title': VideoPanelTitle,
        'character-image': CharacterImage
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
                            thumb: "src/assets/img/thumbnail.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumbnail.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumbnail.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumbnail.png"
                        },
                        {
                            src: "src/assets/video/replay-cross.mp4",
                            thumb: "src/assets/img/thumbnail.png"
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

    html, body {
        height: 100%
    }

    .app {
        display: flex;
        background-color: #1E1E1E;
        height: 100%
    }


    
    #play {
        position: absolute;
        top: 44%;
        left: 40%
    }

    #video-display .video-background {
        opacity: 20%;
    }

    .static-bar {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 20%;
        height: 100%;
        background: linear-gradient(180deg, #182429 14.9%, #193C4B 82.08%)
    }

    .game-logo {
        width: 236px;
        height: 162px;
    }

</style>

