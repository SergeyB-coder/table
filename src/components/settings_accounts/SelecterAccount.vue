<template>
    <div v-show="show_account_selecter" class="cntr_input_account">
        <div class="sub_cntr_input_find">

            <svg class="find_svg" width="10" height="11" viewBox="0 0 10 11" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M4.58333 8.41667C6.42428 8.41667 7.91667 6.92428 7.91667 5.08333C7.91667 3.24238 6.42428 1.75 4.58333 1.75C2.74238 1.75 1.25 3.24238 1.25 5.08333C1.25 6.92428 2.74238 8.41667 4.58333 8.41667Z"
                    stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M8.75 9.25L6.9375 7.4375" stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round"
                    stroke-linejoin="round" />
            </svg>
            <input class="input_find text-2" placeholder="Поиск" />


        </div>
        <div v-for="item in items" v-bind:key="item" class="txt_all cntr_account_item">{{ item }}
        </div>
    </div>
</template>
<script>



export default {
    props: {
        items: Array
    },
    data() {
        return {
        }
    },
    components: {
    }
}

</script>

<style scoped>
.input_find {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background-color: white !important;
    height: 28px;
    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    width: 100%;
    padding: 14px 16px 14px 36px;
    box-sizing: border-box;
    outline: none;
}
.find_svg {
    position: absolute;
    top: 50%;
    left: 16px;
    transform: translateY(-50%);
}

.sub_cntr_input_find {
    position: relative;
    margin: 8px;
}
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

    color: #6B7280;
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



.txt_all {
    color: var(--gray-500, #6B7280);

    margin: 12px;
    /* XS/Medium */
    font-family: Inter;
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px; /* 133.333% */
    letter-spacing: 0.06px;
}

.cntr_input_account {
    position: absolute;
    width: 100%;
    height: 168px;
    bottom: -176px;
    left: 0;
    overflow-y: scroll;
    border-radius: 8px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
    z-index: 15
}

.wrap__cntr-selecter {
    box-sizing: border-box;
    /* overflow: scroll; */
    /* overflow-x: hidden; */
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    /* padding: 0px 0px 8px; */

    position: absolute;
    width: 100%;
    height: 162px;
    left: 0px;
    top: 46px;

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/lg */

    box-shadow: 0px 10px 8px rgba(0, 0, 0, 0.04), 0px 4px 3px rgba(0, 0, 0, 0.1);
    border-radius: 8px;

    z-index: 14;
}

.cntr_account_item {
    padding: 8px 12px;
    cursor: pointer;
}

.cntr_account_item:hover {
    background: #F3F4F6;
    border-radius: 6px;
}

.ml-8 {
    margin-left: 8px;
}
</style>