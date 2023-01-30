<template>
        <div class="slide-container">
            <div class="slide-content">
                <ul class="slide-list">
                    <slot class="slide-item">
                
                    </slot>
                </ul>
            </div>
            <!-- <div class="select-container">
                <div class="circle"></div>
                <div class="circle-selected"></div>
                <div class="circle"></div>
            </div> -->
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

<style>

  .slide-container {
        position: absolute;
        width: 60vw;
        height: 30vh;
        top: 60vh;
        z-index: 2;
        margin-left: 8vw;
    }

    .slide-content {
        width: 100%;
        height: 100%;
        border-radius: 8px;
        overflow: hidden;
        overflow-x: scroll;
    }

    .slide-list {
        list-style: none;
        width: max-content;
    }
    
    .slide-item {
        display: inline-block;
        margin: 20px 40px;    
    }

    .previous-arrow {}
    .next-arrow {}

    .active {}
    .previous {}
    .next {}
     
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

  .selected {
    display: inline-block;
    width: 16px;
    height: 16px;
    border-radius: 50%;
    background-color: #6AD3FC;
  }

</style>