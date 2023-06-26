<template>
    <div class="cntr-row">
        <part-left />
        <div class="cntr-bg-2">

            <div class="cntr-table">
                <div class="btn_back w-97 h-40 cntr-row a-c cur-pointer">
                    <svg class="ml-16" width="8" height="14" viewBox="0 0 8 14" fill="none"
                        xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z"
                            fill="#6B7280" />
                    </svg>
                    <div class="text-3 ml-11 ">Назад</div>
                </div>

                <div style="display: flex; width: 70vw">
                    <div style="width: 50%">

                        
                        <div class="row_between  a-c mt-15">
                            <div style="width: fit-content" class="text-2">
                                Заголовок 2
                            </div>
                            <div class="text-6">
                                0/25
                            </div>
                        </div>
                        <textarea class="textarea_tizer mt-10 text-2" rows="3" placeholder="Введите заголовок"></textarea>
                        <div class="row_between  a-c mt-15">
                            <div style="width: fit-content" class="text-2">
                                Заголовок 3
                            </div>
                            <div class="text-6">
                                0/25
                            </div>
                        </div>
                        <textarea class="textarea_tizer mt-10" rows="3" placeholder="Введите заголовок"></textarea>

                    </div>
                    <div style="width: 50%; margin-left: 8px">
                        <div class="row_between  a-c mt-15">
                            <div style="width: fit-content" class="text-2">
                                Текст 2
                            </div>
                            <div class="text-6">
                                0/60
                            </div>
                        </div>
                        <textarea class="textarea_tizer mt-10 text-2" rows="3" placeholder="Введите заголовок"></textarea>
                        <div class="row_between  a-c mt-15">
                            <div style="width: fit-content" class="text-2">
                                Текст 3
                            </div>
                            <div class="text-6">
                                0/60
                            </div>
                        </div>
                        <textarea class="textarea_tizer mt-10" rows="3" placeholder="Введите заголовок"></textarea>

                    </div>
                </div>

                <div style="display: flex" class="mt-15">
                    <div class="btn_add_tizer text-2">
                        Добавить еще тизеры
                    </div>
                    <div class="btn_generate_tizer text-4">
                        Сгенерировать тизеры
                    </div>
                </div>

                <div style="width: fit-content" class="text-2 mt-10">
                    Ссылка
                </div>
                <div class="row_between a-c mt-10">
                    <input :class="{input_link_futter: show_link_warning, textarea_tizer: !show_link_warning}" placeholder="Ввод" />
                    <div class="check_futter">

                    </div>
                    <div class="check_futter_text">Важная</div>
                </div>

                <div style="width: fit-content" class="text-2 mt-10">
                    Примечание
                </div>
                <div class="row_between a-c mt-10">
                    <input :class="{input_link_futter: show_link_warning, textarea_tizer: !show_link_warning}" placeholder="Ввод" />
                </div>

                <div class="cntr-row mt-15">
                    <div class="btn_save_to text-4">Сохранить и перейти в список доставок</div>
                    <div class="btn_grey text-5">Перейти в созданный список доставок</div>
                </div>
                
                <div class="btn_save_create text-4 mt-15">
                    Сохранить и создать следующую доставку
                </div>
            </div>
        </div>
    </div>
</template>

<script>
// import Vue from 'vue';
// import SvgAccept from './svg/SvgAccept.vue'
// import SvgCancel from './svg/SvgCancel.vue'
// import SvgStop from './svg/SvgStop.vue'
// import SvgAttention from './svg/SvgAttention.vue'

// import SelecterActual from './SelecterActual.vue'
// import SelecterStatus from './SelecterStatus.vue'
import PartLeftListDelivers from '../delivers/PartLeftListDelivers.vue'

export default {
    name: 'TizersDeliver',
    data() {
        return {
            show_rules_tizer_create: true,
            selecter_project_focus: false,
            selecter_line_focus: false,
            selecter_target_focus: false,
            selecter_geos_focus: false,
            focus_input_link: false,

            show_link_warning: false,

            selected_projects: [],
            selected_lines: [],
            selected_targets: [],
            selected_geos: [],
            targets_found: [{ id: 1, name: 'таргет 1' }, { id: 2, name: 'таргет 2' }, { id: 3, name: 'таргет 3' }],

            rules: [
                { id: 1, name: 'использовать ! или 2 можно только 1 раз за тизер' },
                { id: 2, name: 'использовать + - % * ( ) можно любое число раз' },
                { id: 3, name: 'другие спецсимволы и эмодзи использовать нельзя' },
                { id: 4, name: 'при использовании троеточия тизер может не пройти модерацию в некоторых соцсетях' },
                { id: 5, name: 'слова не на русском языке можно использовать только для названий брендов или сфер, апример: IT' },
                { id: 6, name: 'нельзя использовать слова: лучший, самый' },
                { id: 7, name: 'нельзя упоминать секс, наркотики, алкоголь, курение, смерть, мат, а также их синонимы и эвфемизмы' },
                { id: 8, name: 'при упоминании в тизере названия какой-либо соцсети, тизер может не пройти модерацию в соцсетях-конкурентах' },
                { id: 9, name: 'при упоминании ФИО живого человека тизер не пройдет модерацию в соцсетях, если нет заверенного письменного разрешения от этого человека' },
                { id: 10, name: 'заголовок и текст тизера должны быть двумя самостоятельными высказываниями, нельзя создавать заголовок как начало предложения и текст - как его продолжение' },
                { id: 11, name: 'заголовок и текст тизера должны заканчиваться на. ? или !' },
            ]
        }
    },
    components: {
        'part-left': PartLeftListDelivers,
    }
}



</script>

<style scoped>
.check_futter_text {
    color: var(--gray-800, #1F2937);
    font-size: 12px;
    font-family: Inter;
    font-weight: 500;
    line-height: 24px;
    letter-spacing: 0.06px;

    margin-left: 9px;
}

.check_futter {
    margin-left: 17px;
    border-radius: 4px;
    border: 1px solid var(--unnamed, #E5E7EB);
    width: 14px;
    height: 14px;
}

.input_link_futter_warning {
    color: #F87171;

    /* Input/Small Medium */
    font-size: 14px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.07px;
    text-align: left;

    margin-top: 5px;
}

.input_link_futter {
    border-radius: 6px;
    border: 1px solid #F87171;
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    outline: none;

    padding: 14px 16px 14px 16px;
    width: 100%;
}

.input_link_futter::placeholder {
    color: #F87171;

    /* Input/Default Medium */
    font-size: 15px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.075px;
}

.blue_shadow {
    border-radius: 6px;
    border: 1px solid var(--active, #3B82F6);
    /* background: var(--white-white, #FFF); */

    /* обводка инпут */
    box-shadow: 0px 0px 0px 4px rgba(59, 130, 246, 0.25);
}

.btn_add_tizer {
    border-radius: 6px;
    background: var(--gray-100, #F3F4F6);
    padding: 14px 16px 14px 16px;
    cursor: pointer;
}

.btn_add_tizer:hover {
    background: var(--gray-800, #1F2937);
    color: var(--white-white, #FFF);
}

.a-c {
    align-items: center
}

.btn_grey {
    border-radius: 6px;
    padding: 14px 16px 14px 16px;

    margin-left: 8px;

    cursor: pointer;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--gray-50, #F9FAFB);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
}

.btn_save_to {
    border-radius: 6px;
    background: var(--blue-500, #3B82F6);
    padding: 14px 16px 14px 16px;

    /* margin-left: 8px; */

    cursor: pointer;
}

.btn_save_create {
    border-radius: 6px;
    background: var(--gray-600, #4B5563);
    padding: 14px 16px 14px 16px;
}

.btn_generate_tizer {
    border-radius: 6px;
    background: var(--blue-500, #3B82F6);
    padding: 14px 16px 14px 16px;

    margin-left: 8px;

    cursor: pointer;
}
.btn_generate_tizer:hover {
    background: var(--gray-800, #1F2937);
    color: var(--white-white, #FFF);
}

.btn_upload {
    border-radius: 6px;
    background: var(--blue-500, #3B82F6);
    padding: 14px 16px 14px 16px;
    width: 5vw;
}

.cntr_tizer_rules {
    border-radius: 6px;
    background: #F3F4F6;
    padding: 20px;
    margin-top: 15px;
}

.text-6 {
    color: var(--slate-500, #64748B);
    text-align: right;

    /* Input/Small Medium */
    font-size: 14px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.07px;
}

.text-5 {
    color: var(--gray-500, #6B7280);
    text-align: center;

    /* Input/Medium Semi Bold */
    font-size: 15px;
    font-family: Inter;
    font-weight: 600;
    letter-spacing: 0.075px;
}

.rules_text {
    color: var(--gray-500, #6B7280);
    font-size: 15px;
    font-family: Inter;
    font-weight: 500;
    line-height: 134.023%;
    letter-spacing: 0.075px;
    text-align: left;

    margin-top: 15px;
}

.btn_back {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    /* padding: 8px 12px 8px 12px; */

    color: var(--gray-500, #6B7280);
    text-align: center;
    /* Base/Medium */
    font-size: 16px;
    font-family: Inter;
    font-weight: 500;
    line-height: 24px;
    letter-spacing: 0.08px;
}

.input_message {
    width: calc(100% - 33px);
}

.input_message:focus {
    border-radius: 6px;
    border: 1px solid var(--blue-500, #3B82F6) !important;
    background: var(--white-white, #FFF);

    /* обводка инпут */
    box-shadow: 0px 0px 0px 4px rgba(59, 130, 246, 0.25);
}

.target_item {
    padding: 8px 12px 8px 12px;
    cursor: pointer
}

.target_item:hover {
    border-radius: 6px;
    background: #F3F4F6;
}

.text-4 {
    color: var(--white-white, #FFF);
    text-align: center;

    /* Input/Medium Semi Bold */
    font-size: 15px;
    font-family: Inter;
    font-weight: 600;
    letter-spacing: 0.075px;
}

.btn_add_new_segment {
    border-radius: 6px;
    background: var(--gray-500, #6B7280);
    padding: 14px 16px 14px 16px;

    margin-top: 15px;
    width: 50%;
}

.w-50p {
    width: calc(50% - 4px);
}

.cntr_list_targets {
    position: absolute;
    top: calc(100% + 2px);
    left: 0;
    border-radius: 8px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);

    padding: 14px 16px 14px 16px;
    width: calc(100% - 33px);

    color: var(--gray-800, #1F2937);
    /* SM/Medium */
    font-size: 14px;
    font-family: Inter;
    font-weight: 500;
    line-height: 20px;
    letter-spacing: 0.07px;
    text-align: left;
    z-index: 11;
}

.project_item {
    position: absolute;
    top: calc(100% + 2px);
    left: 0;
    border-radius: 8px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);

    padding: 14px 16px 14px 16px;
    width: calc(100% - 33px);

    color: var(--gray-800, #1F2937);
    /* SM/Medium */
    font-size: 14px;
    font-family: Inter;
    font-weight: 500;
    line-height: 20px;
    letter-spacing: 0.07px;
    text-align: left;
    z-index: 10;
}

.selecter_input {
    outline: none;
    border: none;
}

.row_between {
    display: flex;
    justify-content: space-between;
}

.textarea_tizer {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    outline: none;
    resize: none;
    width: calc(100% - 32px);
    padding: 14px 16px 14px 16px;
}

.textarea_tizer:focus {
    border-radius: 6px;
    border: 1px solid var(--active, #3B82F6);
    background: var(--white-white, #FFF);

    /* обводка инпут */
    box-shadow: 0px 0px 0px 4px rgba(59, 130, 246, 0.25);
}

.textarea_tizer::placeholder {
    color: var(--unnamed, #6B7280);

    /* Input/Default Medium */
    font-size: 15px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.075px;
}

.selected_file {
    position: relative;
    border-radius: 0px 6px 6px 0px;

    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    padding: 14px 16px 14px 16px;

    width: 12vw;
}

.row_link_tizer {
    display: flex;
}

.link_tizer {

    border-radius: 0px 6px 6px 0px;

    position: relative;
    border: 1px solid var(--gray-200, #E5E7EB);

    background: var(--white-white, #FFF);
    /* обводка инпут */


    padding: 14px 16px 14px 16px;

    width: calc(30vw - 32px);

    outline: none
}

.cntr_text_http {
    background: var(--gray-50, #F9FAFB);

    border-radius: 6px 0px 0px 6px;

    position: relative;
    border: 1px solid var(--gray-200, #E5E7EB);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    padding: 14px 16px 14px 16px;

    width: calc(6vw - 32px);
}

.selecter_file {
    border-radius: 6px 0px 0px 6px;

    position: relative;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    padding: 14px 16px 14px 16px;

    width: 10vw;
}

.selecter_project {
    position: relative;
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    padding: 14px 16px 14px 16px;
}

.mt-12 {
    margin-top: 12px;
}

.mt-15 {
    margin-top: 15px;
}

.ml-20 {
    margin-left: 20px;
}

.ml-36 {
    margin-left: 36px;
}


.line {
    width: 100%;
    height: 1px;

    background: #E5E7EB;
}

.mt-5 {
    margin-top: 5px;
}

.mt-10 {
    margin-top: 10px;
}

.mt-18 {
    margin-top: 18px;
}

.mt-20 {
    margin-top: 20px;
}

.ml-2v {
    margin-left: 2vw;
}

.ml-5v {
    margin-left: 5vw;
}

.ml-8 {
    margin-left: 8px;
}

.ml-10 {
    margin-left: 10px;
}

.ml-11 {
    margin-left: 11px;
}

.ml-14 {
    margin-left: 14px;
}

.ml-16 {
    margin-left: 16px;
}

.ml-18 {
    margin-left: 18px;
}

.mr-16 {
    margin-right: 16px;
}

.a-c {
    align-items: center;
}

.j-c {
    justify-content: center;
}

.j-b {
    justify-content: space-between;
}

.h-40 {
    height: 40px
}

.w-56 {
    width: 56px;
}

.w-78 {
    width: 78px;
}

.w-87 {
    width: 87px;
}

.w-97 {
    width: 97px;
}

.w-98 {
    width: 98px;
}

.w-113 {
    width: 113px;
}

.w-137 {
    width: 137px;
}

.w-148 {
    width: 148px;
}

.w-150 {
    width: 150px;
}

.w-155 {
    width: 155px;
}

.w-166 {
    width: 166px;
}

.w-179 {
    width: 179px;
}

.w-188 {
    width: 188px;
}

.w-213 {
    width: 213px;
}

.w-233 {
    width: 233px;
}


.h-40 {
    height: 40px;
}

.text-1 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 20px;
    line-height: 24px;
    letter-spacing: 0.005em;

    color: #000000;

    text-align: left;
}

.text-2 {
    color: var(--gray-800, #1F2937);
    /* Input/Small Semi Bold */
    font-size: 14px;
    font-family: Inter;
    font-weight: 600;
    letter-spacing: 0.07px;
}

.text-3 {
    color: var(--gray-500, #6B7280);

    /* Input/Default Medium */
    font-size: 15px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.075px;
}

.text_input {
    color: var(--unnamed, #1F2937);
    font-size: 15px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.075px;
}

.cntr-table {
    padding-left: 26px;
    padding-top: 21px;
    padding-right: 27px;
}

.cntr-bg-2 {
    background: #FFFFFF;
    position: relative;
    width: 70%;
}

.cntr-row {
    display: flex;
    position: relative;
}



.blue-box {
    width: 40px;
    height: 40px;

    /* Blue/500 */

    background: #3B82F6;
    border-radius: 6px;
}
</style>