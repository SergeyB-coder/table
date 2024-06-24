<template>
    <div class="cntr-selecter">
        <div class="cntr-selecter-item box-select">
            <svg-accept/>
        </div>
        <div class="cntr-selecter-item">
            <svg-attention/>
        </div>
        <div class="cntr-selecter-item">
            <svg-stop/>
        </div>
        <div class="cntr-selecter-item">
            <svg-cancel/>
        </div>
    </div>
</template>

<script>
    import SvgAccept from './svg/SvgAccept.vue'
    import SvgCancel from './svg/SvgCancel.vue'
    import SvgStop from './svg/SvgStop.vue'
    import SvgAttention from './svg/SvgAttention.vue'

    export default {
        name: 'SelecterStatus',
        data() {
            return {
            }
        },
        components: {
            'svg-accept': SvgAccept,
            'svg-cancel': SvgCancel,
            'svg-stop': SvgStop,
            'svg-attention': SvgAttention,
        }
    }

</script>

<style scoped>
    .cntr-selecter {
        box-sizing: border-box;

        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 0px 0px 8px;

        position: absolute;
        width: 78px;
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
    }

    .cntr-selecter-item {
        /* padding: 8px 12px; */
        /* gap: 8px; */
        margin-left: 8px;
        margin-top: 8px;
        display: flex;
        justify-content: center;
        align-items: center;
        width: 56px;
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

    

    
</style>