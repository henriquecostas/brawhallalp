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
            <img class="border-detail" 
                src="src/assets/img/border-detail.png" 
                alt="border detail" 
            />
            <img class="border-detail invert" 
                src="src/assets/img/border-detail.png" 
                alt="border detail" 
            />
            <img class='game-logo' 
                :src='game.image.src' 
                :alt='game.image.alt'
            />
        </div>

        <character-image>
            <img 
                :src='game.character.image' 
                :alt='game.character.description'
            />
        </character-image>
        
        <div class="video-list-container">
            <div class="video-list-content">
                <ul class="video-list">
                    <li 
                    class="video-list-item"
                    v-for="video of game.character.video"
                    >
                    <img :src="video.thumb">
                    </li>
                </ul>
            </div>
            <div class="select-container">
                <div class="circle"></div>
                <div class="circle-selected"></div>
                <div class="circle"></div>
            </div>
        </div>
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
    // character: [{
    //                 name: 'CROSS',
    //                 image: "src/assets/img/cross_img.png",
    //                 description: 'Imagem do Cross',
    //                 video:[
    //                     {
    //                         src: "src/assets/video/replay-cross.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-cross.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-cross.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-cross.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-cross.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     }                   
    //                 ]},
    //                 {
    //                 name: 'HUGIN',
    //                 image: "src/assets/img/hugin_img.png",
    //                 description: 'Imagem do hugin',
    //                 video:[
    //                     {
    //                         src: "src/assets/video/replay-hugin.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-hugin.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-hugin.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-hugin.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     },
    //                     {
    //                         src: "src/assets/video/replay-hugin.mp4",
    //                         thumb: "src/assets/img/thumbnail.png"
    //                     }                   
    //                 ]},
                    
    //             ],
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
        height: 100%;
        max-width: 1920px;
        max-height: 1080px;
    }

    .static-bar {
        z-index: 1;
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

    .border-detail {
        position: absolute;
        right: 186px;
        mix-blend-mode: color-dodge;
        transform: matrix(0, -1, -1, 0, 0, 0);
    }

    .invert {
        transform: matrix(0, 1, -1, 0, 0, 0);
    }

    /* video list */

    .video-list-container {
        position: absolute;
        width: 60vw;
        height: 25vh;
        top: 65vh;
        z-index: 2;
        margin-left: 8vw;
    }

    .video-list-content{
        width: 100%;
        height: 100%;
        border-radius: 8px;
        overflow: hidden;
        overflow-x: scroll;
    }

    .video-list{
        list-style: none;
        width: max-content;
    }
    
    .video-list-item{
        display: inline-block;
        margin: 20px 40px;    
    }

/* ===== Scrollbar CSS ===== */
  /* Firefox */
  * {
    scrollbar-width: thin;
    scrollbar-color: #6ad3fc #2f6c84;
  }

  /* Chrome, Edge, and Safari */
  *::-webkit-scrollbar {
    width: 8px;
  }

  *::-webkit-scrollbar-track {
    background: #2f6c84;
  }

  *::-webkit-scrollbar-thumb {
    background-color: #6ad3fc;
    border-radius: 4px;
    border: 0px none #ffffff;
  }

  /* select */
  .select-container {
    border: 2px white dashed;
    width: 20%;
    height: 10%;
    margin: 0 auto;
    margin-top: 16px;
  }
  
  .circle {
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background-color: #2F6C84;
    display: inline-block;
  }

  .circle-selected {
    display: inline-block;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background-color: #6AD3FC;
  }

</style>

