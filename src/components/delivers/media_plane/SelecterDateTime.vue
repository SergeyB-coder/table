<template>
    <div class="cntr_selecter_datetime" :style="{ width: width }">
        <div class="subcntr_sel_dt">
            <SvgArrowLeft/>
            <label>Февраль</label>
            <SvgArrowRight/>
        </div>
        <div class="subcntr_sel_dt">
            <SvgArrowLeft/>
            <label>2024</label>
            <SvgArrowRight/>
        </div>
    </div>
</template>

<script>
import SvgArrowLeft from './SvgArrowLeft.vue';
import SvgArrowRight from './SvgArrowRight.vue';

export default {
    name: "SelecterDateTime",
    components: {
        SvgArrowLeft,
        SvgArrowRight,
    }
};
</script>

<style scoped>
.cntr_selecter_datetime {
    padding: 0 20px;
    gap: 20px;
    z-index: 1000;
    box-sizing: border-box;
    position: absolute;
    width: 243px;
    height: 55px;
    right: 0;
    top: 50px;

    background: #FFFFFF;
    /* Синий */
    border: 1px solid #3B82F6;
    border-radius: 5px;
    display: flex;
    justify-content: space-between;
    align-items: center;

}

.subcntr_sel_dt {
    gap: 8px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>