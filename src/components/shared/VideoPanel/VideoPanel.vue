<template>
        <div class='video-display'>
            <img class='play-btn' 
                src='/src/assets/img/play-btn.png' 
                alt='Iniciar video'
            />
            <div class="colorize"></div>
            <img class="video-display video" 
                src="/src/assets/img/sem-imagem.jpg" 
                alt="Replay do vídeo"
            />
        </div>
</template>

<script>
    export default {
        data() {
            return {
                
            }
        }
    }
</script>

<style scoped>
    .video-display {
        width: 80%;
        height: 100%;
        overflow: hidden;
    }
    .video {
        opacity: 20%;
        width: 100%;
        height: auto;
    }

    .colorize {
        background: rgba(25, 60, 75, 0.27);
        width: 100%;
        height: 100%;
        filter: blur(2px);
        position: absolute;
    }
    .play-btn {
        position: absolute;
        top: 44%;
        left: 40%;
        z-index: 4;
    }

</style>