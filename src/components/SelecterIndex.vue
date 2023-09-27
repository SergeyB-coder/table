<template>
    <div class="cntr-selecter">
        
        <div  class="cntr-selecter-item box_select">
            
            <div class="text-2 color-1 ml-8">индекс1</div>
        </div>


        <div v-for="index in [2, 3, 4, 5, 6, 7, 8, 9, 10]" v-bind:key="index" class="cntr-selecter-item">
            <div class="text-2 color-1 ml-8">индекс{{ index }}</div>
        </div>
        <div @click="is_selected_index = !is_selected_index" class="cntr-selecter-item " :class="{ box_select: !is_selected_index }">
            
            <div class="text-2 color-1 ml-8" 
                :class="{ color2: is_selected_index }"
            >
                Все индексы
            </div>
        </div>
        
    </div>
</template>

<script>
    // import SvgAccept from './svg/SvgAccept.vue'
    // import SvgCancel from './svg/SvgCancel.vue'
    // import SvgStop from './svg/SvgStop.vue'
    // import SvgAttention from './svg/SvgAttention.vue'
    
    export default {
        name: 'SelecterIndex',
        data() {
            return {
                is_selected_index: true
            }
        },
        components: {
            // 'svg-accept': SvgAccept,
            // 'svg-cancel': SvgCancel,
            // 'svg-stop': SvgStop,
            // 'svg-attention': SvgAttention,
        }
    }

</script>

<style scoped>
    .text-2 {
        font-family: 'Inter';
        font-style: normal;
        font-weight: 500;
        font-size: 12px;
        line-height: 16px;
        /* identical to box height, or 133% */

        letter-spacing: 0.005em;
        text-align: left;
        /* Gray/500 */
    }

    .color-1 {
        color: #6B7280;
    }
    .color2 {
        color: #3B82F6;
    }
    .cntr-selecter {
        box-sizing: border-box;
        overflow: scroll;
        overflow-x: hidden;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 0px 0px 8px;

        position: absolute;
        width: 141px;
        height: 162px;
        left: 0px;
        top: 45px;

        /* White/White */

        background: #FFFFFF;
        /* Gray/200 */

        border: 1px solid #E5E7EB;
        /* Drop Shadow/lg */

        box-shadow: 0px 10px 8px rgba(0, 0, 0, 0.04), 0px 4px 3px rgba(0, 0, 0, 0.1);
        border-radius: 8px;

        z-index: 14;
    }

    .cntr-selecter-item {
        padding: 8px 12px;
        /* gap: 8px; */
        margin-left: 8px;
        margin-top: 8px;
        display: flex;
        justify-content: center;
        align-items: center;
        /* width: 56px; */
        height: 32px;        
    }
    .box_select {
        background: #F3F4F6;
        border-radius: 6px;
    }

    .box_select {
        background: #F3F4F6;
        border-radius: 6px;
    }

    .ml-8 {
        margin-left: 8px;
    }

    
</style>