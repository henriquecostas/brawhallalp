<template>
        <div class="video-display">
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
        width: 100%;
        height: auto;
    }

    /* .colorize {
        background: rgba(23, 219, 219, 0.4);
        filter: blur(2px);
    } */
</style>