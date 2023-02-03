<template class="container">
        <div class="slide-container">

            <div class="arrow-previous control">
                <img
                    src="src/assets/svg/arrow-left.svg"
                    alt="Passar slide para esquerda"
                />
            </div>

            <div class="slide-content">
                <ul class="slide-list">
                    <slot class="slide-item"></slot>
                </ul>
            </div>

            <div class="arrow-next control">
                <img 
                    src="src/assets/svg/arrow-right.svg"
                    alt="Passar slide para direita"
                />
            </div>

            <div class="select-container">

            </div>

        </div>
</template>

<script>

    export default { 
        data() {
            return {

            }
        },

        mounted () {
            const controls = document.querySelectorAll(".control");
            let items = document.querySelectorAll('.slide-item');    
            
            const selectContainer = document.querySelector('.select-container');
            let selectItems = []

            items.forEach(() => {
                let select = document.createElement('div')
                selectContainer.appendChild(select)
                select.classList.add('select-item')
                selectItems.push(select)
            })

            let slideItem = {
                current: 0,
                previous: 0,
                next: 0,
                max: items.length
            }

            items[slideItem.current].classList.add('active');
            selectItems[slideItem.current].classList.add('selected');

            controls.forEach(control => {
                control.addEventListener('click', () => {
                    const isRight = control.classList.contains('arrow-next')

                    if (isRight) {
                        slideItem.current += 1;
                    } else {
                        slideItem.current -= 1;
                    }

                    if (slideItem.current >= slideItem.max) {
                        slideItem.current = 0;
                    }

                    if (slideItem.current < 0) {
                        slideItem.current = slideItem.max - 1;
                    }
                    
                    items.forEach((item) => 
                        item.classList.remove('active')
                    );
                        
                    selectItems.forEach((select) => 
                        select.classList.remove('selected')
                    );

                    items[slideItem.current].scrollIntoView({
                        inline: "center",
                        behavior: "smooth"
                    })
                
                    items[slideItem.current].classList.add('active');
                    selectItems[slideItem.current].classList.add('selected');


                })
            })

            selectItems.forEach(select => {
                select.addEventListener('click', () => {
                    const isSelected = select.classList.contains('selected');

                    if (isSelected) {
                        return
                    } else {
                        let selectedItem = document.querySelector('.selected');
                        selectedItem.classList.remove('selected');
                        let index = selectItems.indexOf(select);
                        select.classList.add('selected');

                        items[slideItem.current].classList.remove('active');
                        slideItem.current = index;

                        items[slideItem.current].classList.add('active');
                        
                        items[slideItem.current].scrollIntoView({
                            inline: "center",
                            behavior: "smooth"
                        })

                    }
                })
            })
        }
    }

</script>

<style>
    .slide-container {
        position: absolute;
        display: flex;
        flex-direction: column;
 
        bottom: 0;
        margin-bottom: 20px;
 
        width: 80%;
        height: 160px;
    }

    .slide-container::-webkit-scrollbar {
        display: none;
    }

    .slide-container {
        -ms-overflow-style: none;  /* IE and Edge */
        scrollbar-width: none;  /* Firefox */
    }

    .slide-content {
        width: 80%;
        height: 100%;
        border-radius: 8px;
        overflow: hidden;
        margin: 0 auto;
    }

    .slide-list {
        list-style: none;
        width: max-content;
        max-width: max-content;
    }
    
    .slide-item {
        display: inline-block;
        margin: 0px 40px;    
        opacity: 0.5;
    }
    
    .slide-item img {
        height: 140px;
    }

    .arrow-previous {
        position: absolute;
        background-color: #075e81;
        border-radius: 8px;
        width: 40px;
        height: 40px;
        top: 32%;
        left: 0;
        display: flex;
        display: none;
    }
    
    .arrow-previous:hover {
        background-color: #6AD3FC;
        transition: 0.7s;
    }

    .arrow-next {
        position: absolute;
        background-color: #075e81;
        border-radius: 8px;
        width: 40px;
        height: 40px;
        top: 32%;
        right: 0;
        display: flex;
        display: none;

    }

    .arrow-next:hover {
        background-color: #6AD3FC;
        transition: 0.7s;
    }

    .active {
        opacity: 1;
    }
     
    /* select box */
    .select-container {
        width: max-content;
        margin: 0 auto;
        display: flex;
        gap: 20px;
    }
  
    .select-item {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        background-color: #2F6C84;
        opacity: 0.5;
    }

    .selected {
        width: 12px;
        height: 12px;
        border-radius: 50%;
        background-color: #6AD3FC;
        opacity: 1;
    }

</style>