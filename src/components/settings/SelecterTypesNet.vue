<template>
    <div class="wrap__cntr-selecter">
        <div class="cntr-selecter">
            <div v-for="interest in interests" v-bind:key="interest" class="cntr-selecter-item box-select"
                @click="handleSelection(interest)">
                <div class="text-2 color-1 ml-8">{{ interest }}</div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'SelecterTypeNet',
    props: {
        interests: Array,
        updateVariable: Function
    },
    data() {
        return {

        }
    },
    components: {
    },
    methods: {
        handleSelection(selectedInterest) {
            // Вызываем функцию обновления переменной в родительском компоненте
            this.updateVariable(selectedInterest);
        }
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

::-webkit-scrollbar {
    width: 6px;
    margin-right: 5px;
}



/* Handle */
::-webkit-scrollbar-thumb {
    /* border-radius: 999px; */
    border-radius: 10px;
    background: #E5E7EB;
}





.cntr-selecter {
    box-sizing: border-box;
    overflow: scroll;
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px 0px 8px;

    /* position: absolute; */
    width: 99%;
    height: 162px;


    z-index: 14;
}

.wrap__cntr-selecter {
    box-sizing: border-box;
    /* overflow: scroll; */
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    /* padding: 0px 0px 8px; */

    position: absolute;
    width: 100%;
    height: 162px;
    left: 0px;
    top: 50px;

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
    justify-content: left;
    align-items: center;
    width: 91%;
    height: 32px;
    cursor: pointer;
}

.cntr-selecter-item:hover {
    background: #F3F4F6;
    border-radius: 6px;
}

.ml-8 {
    margin-left: 8px;
}
</style>