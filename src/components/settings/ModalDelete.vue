<template>
    <div class="main__modal">
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

        <div class="question_sign">
            <svg width="62" height="62" viewBox="0 0 62 62" fill="none" xmlns="http://www.w3.org/2000/svg">
                <rect x="3.5" y="3.5" width="55" height="55" rx="27.5" fill="#FEF9C3" />
                <rect x="3.5" y="3.5" width="55" height="55" rx="27.5" stroke="#FEFCE8" stroke-width="7" />
                <g clip-path="url(#clip0_582_173842)">
                    <path
                        d="M32.5958 20.5447C32.4349 20.2645 32.203 20.0317 31.9233 19.8698C31.6437 19.7079 31.3264 19.6227 31.0033 19.6227C30.6802 19.6227 30.3628 19.7079 30.0832 19.8698C29.8036 20.0317 29.5716 20.2645 29.4108 20.5447L18.2681 39.5036C17.5255 40.7679 18.416 42.375 19.8606 42.375H42.1443C43.5889 42.375 44.481 40.7662 43.7368 39.5036L32.5958 20.5447ZM31 26.125C31.8694 26.125 32.5503 26.8757 32.4625 27.7419L31.8938 33.4407C31.8746 33.6646 31.7722 33.8732 31.6067 34.0251C31.4412 34.1771 31.2247 34.2614 31 34.2614C30.7753 34.2614 30.5588 34.1771 30.3933 34.0251C30.2278 33.8732 30.1254 33.6646 30.1063 33.4407L29.5375 27.7419C29.5171 27.5375 29.5397 27.3311 29.6039 27.136C29.6681 26.9409 29.7724 26.7614 29.9102 26.6091C30.048 26.4568 30.2161 26.335 30.4038 26.2516C30.5915 26.1682 30.7946 26.1251 31 26.125ZM31.0033 35.875C31.4342 35.875 31.8476 36.0462 32.1523 36.3509C32.457 36.6557 32.6283 37.069 32.6283 37.5C32.6283 37.931 32.457 38.3443 32.1523 38.649C31.8476 38.9538 31.4342 39.125 31.0033 39.125C30.5723 39.125 30.159 38.9538 29.8542 38.649C29.5495 38.3443 29.3783 37.931 29.3783 37.5C29.3783 37.069 29.5495 36.6557 29.8542 36.3509C30.159 36.0462 30.5723 35.875 31.0033 35.875Z"
                        fill="#F2994A" />
                </g>
                <defs>
                    <clipPath id="clip0_582_173842">
                        <rect width="26" height="26" fill="white" transform="translate(18 18)" />
                    </clipPath>
                </defs>
            </svg>


        </div>

        <div class="cntr_title">
            <div class="modal_accept__title">
                Удалить чат?
            </div>
        </div>

        <!-- <div > -->
        <div class="modal_accept_text">
            Подтвердите удаление чата
        </div>
        <!-- </div> -->


        <div class="main__modal_futter" @click="$show_modal_is_save = false">
            <div class="main__modal_btn_cancel">Удалить</div>
        </div>
    </div>
</template>

<script>

export default {
    props: ['show_modal_is_save'],
    data() {
        return {

        }
    },
    components: {
    }
}

</script>

<style scoped>
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

.main__modal_futter {
    display: flex;
    justify-content: center;
    width: 100%;
    margin-top: 20px;
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
    top: 22px;
    cursor: pointer;
}

.main__modal {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;

    position: absolute;
    width: 33vw;
    height: 302px;
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