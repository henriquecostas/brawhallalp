<template>
<div class="app">
    <div id="video-display">
        <iframe class="video" width="100%" height="100%" src="https://www.youtube.com/embed/m8ywOwK1_bE" 
        fullscreen frameborder="0"></iframe>
    </div>
    <div id="static-bar">
        <img id="game-logo" v-bind:src="game.image.src" :alt="game.image.alt">
    </div>
</div>
</template>

<script>
export default {
    data(){
        return {
            game:{
                video:[
                    {
                        src: "src/assets/video/replay-cross.mp4"
                    },
                    {
                        src: "src/assets/video/replay-cross.mp4"
                    },
                    {
                        src: "src/assets/video/replay-cross.mp4"
                    },
                    {
                        src: "src/assets/video/replay-cross.mp4"
                    },
                    {
                        src: "src/assets/video/replay-cross.mp4"
                    }                   
                ],
                image:{
                    src: "src/assets/img/brawhalla-logo.png",
                    alt: "Logo do jogo Brawhalla"
                }
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
    }

    #video-display {
        width: 80%;
        height: 720px;
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
