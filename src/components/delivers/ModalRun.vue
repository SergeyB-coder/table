<template>
    <div class="main__modal">

        <div class="cntr_row j_b">
            <div class="modal_text_xs"></div>
            <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M12.1223 1.87756C12.1631 1.9182 12.1954 1.96647 12.2174 2.01963C12.2395 2.07278 12.2508 2.12976 12.2508 2.18731C12.2508 2.24485 12.2395 2.30183 12.2174 2.35498C12.1954 2.40814 12.1631 2.45642 12.1223 2.49706L2.49731 12.1221C2.41516 12.2042 2.30374 12.2504 2.18756 12.2504C2.07139 12.2504 1.95997 12.2042 1.87781 12.1221C1.79566 12.0399 1.74951 11.9285 1.74951 11.8123C1.74951 11.6961 1.79566 11.5847 1.87781 11.5026L11.5028 1.87756C11.5435 1.83681 11.5917 1.80449 11.6449 1.78243C11.698 1.76038 11.755 1.74902 11.8126 1.74902C11.8701 1.74902 11.9271 1.76038 11.9802 1.78243C12.0334 1.80449 12.0817 1.83681 12.1223 1.87756Z" fill="#374151"/>
                <path fill-rule="evenodd" clip-rule="evenodd" d="M1.87756 1.87756C1.83681 1.9182 1.80449 1.96647 1.78243 2.01963C1.76038 2.07278 1.74902 2.12976 1.74902 2.18731C1.74902 2.24485 1.76038 2.30183 1.78243 2.35498C1.80449 2.40814 1.83681 2.45642 1.87756 2.49706L11.5026 12.1221C11.5847 12.2042 11.6961 12.2504 11.8123 12.2504C11.9285 12.2504 12.0399 12.2042 12.1221 12.1221C12.2042 12.0399 12.2504 11.9285 12.2504 11.8123C12.2504 11.6961 12.2042 11.5847 12.1221 11.5026L2.49706 1.87756C2.45642 1.83681 2.40814 1.80449 2.35498 1.78243C2.30183 1.76038 2.24485 1.74902 2.18731 1.74902C2.12976 1.74902 2.07278 1.76038 2.01963 1.78243C1.96647 1.80449 1.9182 1.83681 1.87756 1.87756Z" fill="#374151"/>
            </svg>
        </div>

        <div class="main__modal_title">Запустить</div>

        <div class="line mt-10">
        </div>

        <div style="height: 60vh; display: flex; margin-top: 16px;">
            <div class="modal_col_1">
                <div class="modal__subtitle">Автоматический запуск</div>

                <div class="modal_col_1__item modal_brd_r_top mt-16">
                    Вконтакте
                </div>
                <div class="modal_col_1__item modal_brd_r_bottom">
                    Вконтакте
                </div>

                <div class="modal_col_1__item modal_brd_r_top mt-16">
                    Вконтакте
                </div>
                <div class="modal_col_1__item">
                    Мир тесен
                </div>
                <div class="modal_col_1__item">
                    Сми2
                </div>
                <div class="modal_col_1__item modal_brd_r_bottom">
                    Вконтакте
                </div>
            </div>
            <div class="modal_col_2">
                <div class="modal__subtitle">Ручной запуск</div>
                <div class="modal_text_b mt-10">Яндекс Директ</div>
                <div class="modal__button mt-16">Скачать фид</div>

                <div class="modal_text_b mt-10">ОТМ</div>
                <div class="modal__button mt-16">Скачать фид</div>

                <div class="modal_text_b mt-10">Новостные блоки</div>
                <div class="modal__button mt-16">Скачать фид</div>

                <div class="modal_text_b mt-10">Мобильные операторы</div>
                <div class="modal__button mt-16">Скачать фид</div>
            </div>
            <div class="modal_col_2">
                <div class="modal__subtitle_hide">1</div>

                <div class="modal_text_b mt-10">Videoseed</div>
                <div class="modal__button mt-16">Скачать фид</div>

                <div class="modal_text_b mt-10">Vortimer</div>
                <div class="modal__button mt-16">Скачать фид</div>

                <div class="modal_text_b mt-10">Between</div>
                <div class="modal__button mt-16">Скачать фид</div>

                <div class="modal_text_b mt-10">Тизерные сети (ENG)</div>
                <div class="modal__button mt-16">Скачать фид</div>
            </div>
        </div>

        <div class="main__modal_futter">
            <div class="main__modal_btn_cancel">Отмена</div>
            <div class="main__modal_btn_add">Запустить</div>
        </div>

    </div>
</template>

<script>

export default {
    data() {
        return {
            name_success: true,
            name_wrong: false,
            show_hint: false,
            show_dd_indexes: false,
            items: [
                { id: 1, text: 'кам', hover: true },
                { id: 2, text: 'сам', hover: false },
                { id: 3, text: 'сам', hover: false },
                { id: 4, text: 'сам', hover: false },
                { id: 5, text: 'сам', hover: false },
            ],
            indexes: [
                {id: 1, text: 'кам'},
                {id: 2, text: 'сам'},
                {id: 3, text: 'кам'},
            ]
        }
    },
    components: {
    }
}

</script>

<style scoped>
.modal__button {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    padding: 10px 12px;
    gap: 8px;

    width: 102px;
    /* height: 35px; */

    /* Gray/100 */

    background: #F3F4F6;
    border-radius: 6px;

    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 12px;
    line-height: 15px;
    /* identical to box height */

    text-align: center;
    letter-spacing: 0.005em;

    /* Gray/800 */

    color: #1F2937;
}
.modal_text_b {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    /* identical to box height, or 150% */

    letter-spacing: 0.005em;

    text-align: left;
    /* Gray/800 */

    color: #1F2937;
}
.modal__subtitle {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 15px;
    line-height: 18px;
    letter-spacing: 0.005em;
    height: 2.5vh;
    color: #475569;
}
.modal__subtitle_hide {
    height: 2.5vh;
    color: #FFFFFF;
}
.modal_col_1 {
    width: 18vw;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;
    /* gap: 16px; */
}

.modal_col_2 {
    width: 14vw;

    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px;
    /* gap: 16px; */

}

.modal_col_1__item {
    display: flex;
    flex-direction: row;
    align-items: flex-start;
    padding: 14px 16px;
    gap: 16px;

    
    width: 13vw;
    /* height: 52px; */

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
}

.modal_brd_r_top {
    border-radius: 6px 6px 0px 0px;
}

.modal_brd_r_bottom {
    border-radius: 0px 0px 6px 6px;;
}


.modal_text_xs {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 10px;
    line-height: 12px;
    text-align: left;
    letter-spacing: 0.005em;

    /* Slate/500 */

    color: #64748B;
}
.j_b {
    justify-content: space-between;
}

.mt-10 {
    margin-top: 10px;
}

.mt-16 {
    margin-top: 16px;
}

.line {
    /* width: 1050px; */
    height: 1px;
    width: 100%;
    background: #E5E7EB;
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

}

.main__modal_futter {
    margin-top: 35px;
    margin-left: -4vw;
    /* margin-bottom: -3vw; */
    display: flex;
    justify-content: right;
    align-items: center;
    height: 78px;

    /* Gray/50 */

    background: #F9FAFB;
    /* Gray/200 */

    border-top: 1px solid #E5E7EB;
    width: calc(100% + 6vw);
}


.cntr_row {
    display: flex;
    align-items: center;
    width: 100%;
}

.main__modal {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 23px 23px 0px 40px;

    position: absolute;
    width: 51vw;
    /* height: 82vh; */
    left: calc(50% - 701px/2 + 121.5px);
    top: calc(50% - 585px/2 - 0.5px);

    /* White/White */

    background: #FFFFFF;
    /* Drop Shadow/xl */

    box-shadow: 0px 20px 13px rgba(0, 0, 0, 0.03), 0px 8px 5px rgba(0, 0, 0, 0.08);
    border-radius: 16px;
    overflow: hidden;
    z-index: 11;
}

.main__modal_title {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0.005em;

    color: #000000;

    text-align: left;
}
 
</style>