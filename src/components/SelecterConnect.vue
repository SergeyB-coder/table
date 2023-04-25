<template>
    <div class="cntr-selecter">
        <div class="box-select text-2 cntr-selecter-item">Неподключено</div>
        <div class="text-blue cntr-selecter-item">Подключено</div>
    </div>
</template>

<style scoped>
    .cntr-selecter {
        box-sizing: border-box;

        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 0px 0px 8px;

        position: absolute;
        width: 133px;
        height: 78px;
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
        padding-left: 8px;
        /* gap: 8px; */
        margin-left: 8px;
        margin-top: 8px;
        display: flex;
        justify-content: left;
        align-items: center;
        width: 113px;
        height: 32px;
    }

    .box-select {
        background: #F3F4F6;
        border-radius: 6px;
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

    .text-blue {
        font-family: 'Inter';
        font-style: normal;
        font-weight: 500;
        font-size: 12px;
        line-height: 16px;
        /* identical to box height, or 133% */

        letter-spacing: 0.005em;
        text-align: left;
        /* Active */

        color: #3B82F6;
    }
</style>