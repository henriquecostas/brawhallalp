<template>
    <div class="app">
        <div id="description">
            <H1> {{ title.h3}} </H1>
            <span> CROSS </span>
            <H3> {{ title.description}}</H3>
        </div>
        <div id="video-display">
            <img id="play" src="./assets/img/play-btn.png" alt="Iniciar vídeo">
            <div class="colorize">
                <img src="./assets/img/sem-imagem.jpg" alt="Replay do vídeo">
            </div>
        </div>
        <div id="static-bar">
            <img id="game-logo" v-bind:src="game.image.src" :alt="game.image.alt">
        </div>
        <div id="character-image">
            <img :src="game.character.cross.image" alt="Imagem do Cross">
        </div>
</div>
</template>

<script>
export default {
    data(){
        return {
            game:{
                character: {
                    cross:{
                        image: "src/assets/img/cross_img1.png"
                    } ,
                },
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
                image:{
                    src: "src/assets/img/brawhalla-logo.png",
                    alt: "Logo do jogo Brawhalla"
                }
            },
            title: {
               h3: "TOP 5",
               description: "BEST COMBOS"
            }
        }
    }
}
</script>

<style>
    * {
        margin: 0px;
        padding:  0px;
    }

    .app {
        display: flex;
        box-sizing: border-box;
        background-color: #1E1E1E;
    }
    
    #description {
        position: absolute;
        margin-left: 100px;
        text-align: center;
        top: 270px;
        font-size: 32px;
        color: aliceblue;
    }

    #description h1 {
        font-family: 'Lato', sans-serif;    
        font-size: 32px;
        font-weight: 900;
        padding-bottom: 8px;
    }

    #description h3 {
        font-family: 'Lato', sans-serif;
        font-weight: 300;
        font-size: 32px;
    }

    #description span {
        font-family: 'Lancelot', cursive;
        font-size: 48px;
        font-weight: 400;

        background: linear-gradient(180deg, #5198B4 24.48%, #1C3843 100%);
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        text-fill-color: transparent;
    }

    #character-image {
        display: flex;
        flex-direction: row-reverse;
    }
    
    #character-image img {
        position: absolute;
        padding: 88px 0px;
        margin-right: 12%;
        width: 480px;
        height: auto;
    }

    #video-display {
        width: 80%;
        height: 720px;
        opacity: 16%;
        overflow: hidden;
    }

    #play {
        position: absolute;
        top: 320px;
        left: 40%;
        transform: matrix(1, 0, 0, -1, 0, 0);
    }

    .colorize {
        background: rgba(19, 52, 52, 0.4);
        /* filter: blur(15px); */
    }
    #video-display .video {
        opacity: 20%;
    }

    #static-bar {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 20%;
        height: 720px;
        background: linear-gradient(180deg, #182429 14.9%, #193C4B 82.08%)
    }

    #game-logo {
        width: 236px;
        height: 162px;
    }

</style>

