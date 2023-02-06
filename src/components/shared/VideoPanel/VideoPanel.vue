<template>
        <div class='video-display'>
            <div class="watch-video">
                <img
                    v-on:click="watchToggle" 
                    class='play-btn' 
                    src='/src/assets/img/play-btn.png' 
                    alt='Iniciar video'
                />
            </div>
            <!-- <div class="colorize"></div> -->
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
                let video = document.querySelector('.video');

                if (video.classList.contains('watch')) {
                    video.classList.remove('watch')
                } else {
                    video.classList.add('watch')
                    video.setAttribute('v-on:click','watchToggle')
                }
            }
        }
    }

</script>

<style scoped>
    .video-display {
        width: 100%;
        max-width: 100%;

        height: 100%;

        display: flex;
        justify-content: center;
        align-items: center;

        overflow: hidden;
        
    }
    .video {
        opacity: 20%;
        filter: blur(8px);
        width: 100%;
        max-width: 100%;
        min-width: 100%;
    }
    .watch {
        z-index: 100;
        opacity: 100%;
        filter: blur(0px);
        width: 100vw;
        position: absolute;
        left: 0;
    }

    .watch-video {
        width: 100px;
        height: 100px;

        display: flex;
        justify-content: center;
        align-items: center;
        
        position: absolute;
        margin-left: 10%;
    }
    .play-btn {
        position: absolute;
        margin-left: 20%;
        z-index: 4;
    }

    .play-btn:hover {
        opacity: 100%;
    }

    @media (max-width: 360px) {
        .watch-video {
            margin-left: 0;
        }
        .play-btn {
            margin-left: 0;
        }
    }



</style>