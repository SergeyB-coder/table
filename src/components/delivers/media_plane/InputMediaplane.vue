<template>
    <div class="cntr_selecter_datetime" :style="{ width: width }">
        <input class="td_input_report"/>
    </div>
</template>

<script>

export default {
    name: "SelecterDateTime",
};
</script>

<style scoped>
.cntr_selecter_datetime {
    gap: 20px;
    z-index: 1000;
    box-sizing: border-box;
    position: absolute;
    width: 100%;
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
    gap: 6px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.td_input_report {
    position: absolute;
    top: 12px;
    outline: none;
    border: none;
    color: var(--gray-800, #1F2937);

    /* SM/Medium */
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    /* 142.857% */
    letter-spacing: 0.07px;
    background-color: white !important;
    width: 95%;

}
</style>