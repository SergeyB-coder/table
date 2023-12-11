<template>
    <div class="cntr_input_line">
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
        <div class="sub_cntr_input_find">

            <svg class="find_svg" width="10" height="11" viewBox="0 0 10 11" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M4.9987 9.97908C2.52786 9.97908 0.519531 7.97075 0.519531 5.49992C0.519531 3.02909 2.52786 1.02075 4.9987 1.02075C7.46953 1.02075 9.47786 3.02909 9.47786 5.49992C9.47786 7.97075 7.46953 9.97908 4.9987 9.97908ZM4.9987 1.64575C2.8737 1.64575 1.14453 3.37492 1.14453 5.49992C1.14453 7.62492 2.8737 9.35408 4.9987 9.35408C7.1237 9.35408 8.85286 7.62492 8.85286 5.49992C8.85286 3.37492 7.1237 1.64575 4.9987 1.64575Z"
                    fill="#6B7280" />
                <path
                    d="M6.66536 5.8125H3.33203C3.1612 5.8125 3.01953 5.67083 3.01953 5.5C3.01953 5.32917 3.1612 5.1875 3.33203 5.1875H6.66536C6.8362 5.1875 6.97786 5.32917 6.97786 5.5C6.97786 5.67083 6.8362 5.8125 6.66536 5.8125Z"
                    fill="#6B7280" />
                <path
                    d="M5 7.47909C4.82917 7.47909 4.6875 7.33742 4.6875 7.16659V3.83325C4.6875 3.66242 4.82917 3.52075 5 3.52075C5.17083 3.52075 5.3125 3.66242 5.3125 3.83325V7.16659C5.3125 7.33742 5.17083 7.47909 5 7.47909Z"
                    fill="#6B7280" />
            </svg>

            <div class="text-2 btn_add_line">Добавить новую линию</div>


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
.btn_add_line {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    /* background-color: white !important; */
    /* height: 28px; */
    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    width: 100%;
    padding: 8px 16px 8px 36px;
    box-sizing: border-box;
    cursor: pointer;
}

.btn_add_line:hover {
    background: #F3F4F6;
}
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
    line-height: 16px;
    /* 133.333% */
    letter-spacing: 0.06px;
}

.cntr_input_line {
    position: absolute;
    width: 260px;
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
}</style>