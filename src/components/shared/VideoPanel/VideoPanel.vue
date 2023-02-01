<template>
        <div class='video-display'>
            <img
                v-on:click="watchToggle" 
                class='play-btn' 
                src='/src/assets/img/play-btn.png' 
                alt='Iniciar video'
            />
            <div class="colorize"></div>
            <slot>
            </slot>
        </div>
</template>

<script>
    export default {
        data() {
            return {
                
            }
        },
        
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
        }
    }





</script>

<style scoped>
    .video-display {
        min-width: 100%;
        max-width: 100%;
        height: 100%;
        overflow: hidden;
    }
    .video {
        opacity: 20%;
        filter: blur(8px);
        width: 100%;
        height: auto;
        max-width: 100%;
        min-width: 100%;
    }
    .watch {
        z-index: 100;
        position: absolute;
        min-width: 100%;
        opacity: 100%;
        filter: blur(0px);
    }
    .colorize {
        background: rgba(25, 60, 75, 0.27);
        width: 100vw;
        height: 66.7%;
        position: absolute;
        max-width: 1440px;
        max-height: 720px;
    }
    .play-btn {
        position: absolute;
        top: 30vh;
        left: 50%;
        z-index: 4;
        opacity: 50%;
    }

    .play-btn:hover {
        opacity: 100%;
    }

</style>