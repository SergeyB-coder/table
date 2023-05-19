<template>
    <div class="cntr-selecter">
        
        <div  class="cntr-selecter-item box-select">
            <div class="text-2 color-1 ml-8">1</div>
        </div>


        <div class="cntr-selecter-item">
            <div class="text-2 color-2 ml-8">5</div>
        </div>
        <div class="cntr-selecter-item">
            <div class="text-2 color-2 ml-8">10</div>
        </div>
        <div class="cntr-selecter-item">
            <div class="text-2 color-2 ml-8">25</div>
        </div>
    </div>
</template>

<script>
    // import SvgAccept from './svg/SvgAccept.vue'
    // import SvgCancel from './svg/SvgCancel.vue'
    // import SvgStop from './svg/SvgStop.vue'
    // import SvgAttention from './svg/SvgAttention.vue'
    
    export default {
        name: 'SelecterNumPages',
        data() {
            return {
                
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
    .color-2 {
        color: #3B82F6;
    }
    ::-webkit-scrollbar-thumb {
        background: #E5E7EB;
        border-radius: 999px;
    }
    ::-webkit-scrollbar {
        width: 6px;
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
        width: 113px;
        height: 162px;
        left: 0px;
        top: -165px;

        /* White/White */

        background: #FFFFFF;
        /* Gray/200 */

        border: 1px solid #E5E7EB;
        /* Drop Shadow/lg */

        box-shadow: 0px 10px 8px rgba(0, 0, 0, 0.04), 0px 4px 3px rgba(0, 0, 0, 0.1);
        border-radius: 8px;
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
    .box-select {
        background: #F3F4F6;
        border-radius: 6px;
    }

    .box-select {
        background: #F3F4F6;
        border-radius: 6px;
    }

    .ml-8 {
        margin-left: 8px;
    }

    
</style>