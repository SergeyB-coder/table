<template>
    <div class="cntr-selecter">

        <div v-for="index in ['CPC', 'CPM', 'Нет']" v-bind:key="index" class="cntr-selecter-item">
            <div class=" text-2 color-1 ml-8" :class="{color2 :index==10}">{{ index }}</div>
        </div>

    </div>
</template>

<script>
// import SvgAccept from './svg/SvgAccept.vue'
// import SvgCancel from './svg/SvgCancel.vue'
// import SvgStop from './svg/SvgStop.vue'
// import SvgAttention from './svg/SvgAttention.vue'

export default {
    name: 'SelecterCPC',
    data() {
        return {
            is_selected_page: true
        }
    },
    components: {
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
    justify-content:left;
    align-items: center;
    width: 100px;
    height: 32px;
}

.cntr-selecter-item:hover {
    background: var(--d-9-d-9-d-9, #F3F4F6);
    border-radius: 6px;
}

.ml-8 {
    margin-left: 8px;
}
</style>