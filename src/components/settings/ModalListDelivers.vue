<template>
    <div class="main__modal_list_delivers" style="padding: 20px; box-sizing: border-box;">
        <div class="txt_input">{{ text }}</div>
        <div class="modal__svg_close">
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M12.1218 1.87756C12.1626 1.9182 12.1949 1.96647 12.2169 2.01963C12.239 2.07278 12.2504 2.12976 12.2504 2.18731C12.2504 2.24485 12.239 2.30183 12.2169 2.35498C12.1949 2.40814 12.1626 2.45642 12.1218 2.49706L2.49683 12.1221C2.41468 12.2042 2.30325 12.2504 2.18708 12.2504C2.0709 12.2504 1.95948 12.2042 1.87733 12.1221C1.79518 12.0399 1.74902 11.9285 1.74902 11.8123C1.74902 11.6961 1.79518 11.5847 1.87733 11.5026L11.5023 1.87756C11.543 1.83681 11.5912 1.80449 11.6444 1.78243C11.6975 1.76038 11.7545 1.74902 11.8121 1.74902C11.8696 1.74902 11.9266 1.76038 11.9798 1.78243C12.0329 1.80449 12.0812 1.83681 12.1218 1.87756Z"
                    fill="#374151" />
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.87756 1.87756C1.83681 1.9182 1.80449 1.96647 1.78243 2.01963C1.76038 2.07278 1.74902 2.12976 1.74902 2.18731C1.74902 2.24485 1.76038 2.30183 1.78243 2.35498C1.80449 2.40814 1.83681 2.45642 1.87756 2.49706L11.5026 12.1221C11.5847 12.2042 11.6961 12.2504 11.8123 12.2504C11.9285 12.2504 12.0399 12.2042 12.1221 12.1221C12.2042 12.0399 12.2504 11.9285 12.2504 11.8123C12.2504 11.6961 12.2042 11.5847 12.1221 11.5026L2.49706 1.87756C2.45642 1.83681 2.40814 1.80449 2.35498 1.78243C2.30183 1.76038 2.24485 1.74902 2.18731 1.74902C2.12976 1.74902 2.07278 1.76038 2.01963 1.78243C1.96647 1.80449 1.9182 1.83681 1.87756 1.87756Z"
                    fill="#374151" />
            </svg>
        </div>

        <div class="line" style="width: calc(100% + 40px); transform: translateX(-20px); margin-top: 20px;">

        </div>

        <textarea class="txtarea_delivers" style="margin-top: 20px; height: 214px; border: 3px solid #2563EB80;"
            placeholder="Внесите данные в столбец или через разделитель;"></textarea>

        <div class="line" style="width: calc(100% + 40px); transform: translateX(-20px); margin-top: 20px;">

        </div>

        <div class="cntr-row" style="justify-content: right; gap: 8px; width: 100%; margin-top: 20px;">
            <div class="btn__modal_list_delivers padding_btn grey-box " @click="$show_modal_is_save = false">
                <div class="text-2">Сохранить</div>
            </div>
            <div class="btn__modal_list_delivers padding_btn grey-box " @click="$show_modal_is_save = false">
                <div class="text-2">Отменить</div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        text: String
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
.txtarea_delivers::placeholder {
    font-family: Inter;
    font-size: 12px;
    font-style: italic;
    font-weight: 300;
    line-height: 14.52px;
    letter-spacing: 0.005em;
    text-align: left;

}

.cntr-row {
    display: flex;
    position: relative;
}

.padding_btn {
    padding: 10px 17px;
}

.grey-box {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
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

.txtarea_delivers {
    outline: none;
    resize: none;
    width: -webkit-fill-available;
    height: 284px;

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;

    padding: 14px 16px 0px 16px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 23px;
    letter-spacing: 0.005em;

    color: #1F2937;
}

.line {
    margin-top: -1px;
    height: 1px;

    background: #E5E7EB;
}

.txt_input {
    color: var(--gray-800, #1F2937);

    /* SM/Medium */
    font-family: Inter;
    font-size: 14px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    /* 142.857% */
    letter-spacing: 0.07px;
}

.main__modal_btn_add {
    margin-right: 20px;
    margin-left: 10px;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 12px;
    gap: 8px;

    height: 18px;

    /* Blue/500 */

    background: #3B82F6;
    border-radius: 6px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    text-align: center;
    letter-spacing: 0.005em;

    /* White/White */

    color: #FFFFFF;
}

.main__modal_btn_cancel {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 12px;
    gap: 8px;

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 15px;
    line-height: 18px;
    text-align: center;
    letter-spacing: 0.005em;

    height: 18px;

    color: #1F2937;
    cursor: pointer;

}

.main__modal_btn_cancel:hover {
    background: var(--d-9-d-9-d-9, #F3F4F6);
    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
}

.btn__modal_list_delivers {
    display: flex;
    justify-content: center;
    margin-top: 20px;
    cursor: pointer;
}

.btn__modal_list_delivers:active {
    background-color: #F3F4F6;
}

.btn__modal_list_delivers:hover {
    background-color: #F2F7FF;
}
.modal_accept_text {
    margin-top: 10px;
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 16px;
    line-height: 24px;
    /* or 150% */

    text-align: center;
    letter-spacing: 0.005em;

    /* Gray/500 */

    color: #6B7280;

    /* margin-left: 3vw;
    margin-right: 3vw; */
    width: 100%
}

.cntr_title {
    display: flex;
    width: 100%;
    justify-content: center;
    margin-top: 20px;
}

.modal_accept__title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 700;
    font-size: 24px;
    line-height: 29px;
    /* identical to box height */

    text-align: center;
    letter-spacing: 0.005em;

    /* Gray/800 */

    color: #1F2937;
}

.question_sign {
    display: flex;
    justify-content: center;
    width: 100%;
    margin-top: 40px;
}

.modal__svg_close {
    position: absolute;
    right: 22px;
    top: 22px
}

.main__modal_list_delivers {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;

    position: absolute;
    width: 33vw;
    /* height: 302px; */
    left: calc(50% - 400px/2 + 123px);
    top: calc(50% - 339px/2 - 0.5px);

    /* White/White */

    background: #FFFFFF;
    /* Drop Shadow/xl */

    box-shadow: 0px 20px 13px rgba(0, 0, 0, 0.03), 0px 8px 5px rgba(0, 0, 0, 0.08);
    border-radius: 16px;
    z-index: 13;
}
</style>