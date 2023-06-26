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
                    <div class="text_3 ml-11 ">Назад</div>
                </div>

                <div v-show="!show_rules_tizer_create" class="text-1 mt-12">Список подготовленных доставок</div>

                <div class="line mt-10">
                </div>

                <div v-show="list_delivers.length !== 0">

                    <div style="text-align: left; margin-top: 27px;" class="cntr-row">
                        <div style="width: 5vw;" class="text-6">
                            ID
                        </div>
                        <div style="width: 5vw;" class="text-6">
                            Линия
                        </div>
                        <div style="width: 8vw;" class="text-6">
                            Подлиния
                        </div>
                        <div style="width: 6vw;" class="text-6">
                            Сегмент
                        </div>
                        <div style="width: 7vw;" class="text-6">
                            Гео
                        </div>
                        <div style="width: 7vw;" class="text-6">
                            Формат
                        </div>
                        <div style="width: 15vw;" class="text-6">
                            Тизеры/Пост
                        </div>
                        <div style="width: 7vw;" class="text-6">
                            Важность
                        </div>
                        <div style="width: 7vw;" class="text-6">
                            Примечание
                        </div>
                    </div>

                    <div v-show="!show_rules_tizer_create" class="line mt-10">
                    </div>

                    <div v-for="deliver in list_delivers" v-bind:key="deliver.id"
                        style="text-align: left; position: relative;" class="cntr-row text-grey_14 mt-12">
                        <div style="width: 5vw; padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.id }}
                        </div>
                        <div style="width: 5vw;padding-right: 18px; box-sizing: border-box;">
                            {{ deliver.line }}
                        </div>
                        <div style="width: 8vw;padding-right: 18px; box-sizing: border-box;">
                            {{ deliver.subline }}
                        </div>
                        <div style="width: 6vw;padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.segment }}
                        </div>
                        <div style="width: 7vw;padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.geo }}
                        </div>
                        <div style="width: 7vw;padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.format }}
                        </div>
                        <div style="width: 15vw;padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.tiz_post }}
                        </div>
                        <div style="width: 7vw;padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.is_important }}
                        </div>
                        <div style="width: 7vw;padding-right: 20px; box-sizing: border-box;">
                            {{ deliver.comment }}
                        </div>

                        <div style="position: absolute; right: 0; top: 0px; width: 16px;">
                            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path
                                    d="M16 8C16 12.4183 12.4183 16 8 16C3.58172 16 0 12.4183 0 8C0 3.58172 3.58172 0 8 0C12.4183 0 16 3.58172 16 8Z"
                                    fill="#84CC16" />
                                <path
                                    d="M11.8998 4.98919C11.964 5.05355 12 5.14073 12 5.23161C12 5.32249 11.964 5.40967 11.8998 5.47403L11.1834 6.191L9.80975 4.8175L10.5261 4.10054C10.5905 4.03616 10.6779 4 10.7689 4C10.86 4 10.9473 4.03616 11.0117 4.10054L11.8998 4.98919ZM10.6978 6.67584L9.32416 5.30234L4.64474 9.98184C4.60694 10.0196 4.57848 10.0657 4.56164 10.1164L4.00873 11.7743C3.99871 11.8045 3.99728 11.8369 4.00462 11.8679C4.01196 11.8989 4.02777 11.9272 4.05029 11.9497C4.07281 11.9722 4.10115 11.988 4.13214 11.9954C4.16313 12.0027 4.19555 12.0013 4.22577 11.9913L5.8838 11.4384C5.93446 11.4218 5.98055 11.3936 6.01842 11.356L10.6978 6.67584Z"
                                    fill="white" />
                            </svg>
                            <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <g clip-path="url(#clip0_763_102239)">
                                    <path
                                        d="M16 8C16 10.1217 15.1571 12.1566 13.6569 13.6569C12.1566 15.1571 10.1217 16 8 16C5.87827 16 3.84344 15.1571 2.34315 13.6569C0.842855 12.1566 0 10.1217 0 8C0 5.87827 0.842855 3.84344 2.34315 2.34315C3.84344 0.842855 5.87827 0 8 0C10.1217 0 12.1566 0.842855 13.6569 2.34315C15.1571 3.84344 16 5.87827 16 8ZM5.354 4.646C5.26011 4.55211 5.13278 4.49937 5 4.49937C4.86722 4.49937 4.73989 4.55211 4.646 4.646C4.55211 4.73989 4.49937 4.86722 4.49937 5C4.49937 5.13278 4.55211 5.26011 4.646 5.354L7.293 8L4.646 10.646C4.59951 10.6925 4.56264 10.7477 4.53748 10.8084C4.51232 10.8692 4.49937 10.9343 4.49937 11C4.49937 11.0657 4.51232 11.1308 4.53748 11.1916C4.56264 11.2523 4.59951 11.3075 4.646 11.354C4.73989 11.4479 4.86722 11.5006 5 11.5006C5.06574 11.5006 5.13084 11.4877 5.19158 11.4625C5.25232 11.4374 5.30751 11.4005 5.354 11.354L8 8.707L10.646 11.354C10.6925 11.4005 10.7477 11.4374 10.8084 11.4625C10.8692 11.4877 10.9343 11.5006 11 11.5006C11.0657 11.5006 11.1308 11.4877 11.1916 11.4625C11.2523 11.4374 11.3075 11.4005 11.354 11.354C11.4005 11.3075 11.4374 11.2523 11.4625 11.1916C11.4877 11.1308 11.5006 11.0657 11.5006 11C11.5006 10.9343 11.4877 10.8692 11.4625 10.8084C11.4374 10.7477 11.4005 10.6925 11.354 10.646L8.707 8L11.354 5.354C11.4005 5.30751 11.4374 5.25232 11.4625 5.19158C11.4877 5.13084 11.5006 5.06574 11.5006 5C11.5006 4.93426 11.4877 4.86916 11.4625 4.80842C11.4374 4.74768 11.4005 4.69249 11.354 4.646C11.3075 4.59951 11.2523 4.56264 11.1916 4.53748C11.1308 4.51232 11.0657 4.49937 11 4.49937C10.9343 4.49937 10.8692 4.51232 10.8084 4.53748C10.7477 4.56264 10.6925 4.59951 10.646 4.646L8 7.293L5.354 4.646Z"
                                        fill="#EF4444" />
                                </g>
                                <defs>
                                    <clipPath id="clip0_763_102239">
                                        <rect width="16" height="16" fill="white" />
                                    </clipPath>
                                </defs>
                            </svg>

                        </div>
                    </div>

                    <div class="line mt-10">
                    </div>

                    <div class="row_between h-46 mt-15">
                        <div class="cntr-row">
                            <div class="btn_create_more text-4">
                                Создать еще доставку
                            </div>
                            <div class="btn_clear_list text-orange">
                                Очистить список
                            </div>
                        </div>

                        <div class="btn_run_delivers text-4">
                            Запустить созданные доставки
                        </div>
                    </div>

                </div>

                <div style="margin-top: 90px;" v-show="list_delivers.length === 0">
                    <svg width="77" height="88" viewBox="0 0 77 88" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M52.243 52.6852L46.5801 47.2246" stroke="#D1D5DB" stroke-width="3"
                            stroke-linecap="round" />
                        <path
                            d="M48.7466 12.3374C52.2188 16.8059 54.2861 22.4201 54.2861 28.517C54.2861 43.0935 42.4695 54.9101 27.8931 54.9101C13.3166 54.9101 1.5 43.0935 1.5 28.517C1.5 13.9406 13.3166 2.12402 27.8931 2.12402C33.2231 2.12402 38.1842 3.70403 42.3334 6.42124"
                            stroke="#D1D5DB" stroke-width="3" stroke-linecap="round" />
                        <path
                            d="M70.8983 59.5485L61.084 51.0592C57.9904 48.3832 53.3131 48.7218 50.6371 51.8155L50.637 51.8155C47.961 54.9092 48.2996 59.5865 51.3933 62.2625L61.2075 70.7518C64.3012 73.4278 68.9785 73.0892 71.6545 69.9955L71.6545 69.9955C74.3306 66.9018 73.992 62.2245 70.8983 59.5485Z"
                            fill="#D1D5DB" />
                        <path
                            d="M27.69 87.8757C41.2612 87.8757 52.2628 85.7478 52.2628 83.1229C52.2628 80.498 41.2612 78.3701 27.69 78.3701C14.1188 78.3701 3.11719 80.498 3.11719 83.1229C3.11719 85.7478 14.1188 87.8757 27.69 87.8757Z"
                            fill="#D1D5DB" />
                        <path d="M23.3418 37.3143C25.233 39.7067 29.3226 40.8043 32.4428 37.3143" stroke="#D1D5DB"
                            stroke-width="3" stroke-linecap="round" />
                        <path
                            d="M20.3085 27.4047C21.3138 27.4047 22.1287 26.3181 22.1287 24.9777C22.1287 23.6374 21.3138 22.5508 20.3085 22.5508C19.3032 22.5508 18.4883 23.6374 18.4883 24.9777C18.4883 26.3181 19.3032 27.4047 20.3085 27.4047Z"
                            fill="#D1D5DB" />
                        <path
                            d="M35.6796 27.6068C36.6849 27.6068 37.4998 26.5202 37.4998 25.1799C37.4998 23.8395 36.6849 22.7529 35.6796 22.7529C34.6743 22.7529 33.8594 23.8395 33.8594 25.1799C33.8594 26.5202 34.6743 27.6068 35.6796 27.6068Z"
                            fill="#D1D5DB" />
                    </svg>

                    <div class="text_grey_16">Нет подготовленных доставок </div>

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
    name: 'ListDelivers',
    data() {
        return {
            show_rules_tizer_create: false,
            selecter_project_focus: false,
            selecter_line_focus: false,
            selecter_target_focus: false,
            selecter_geos_focus: false,
            selected_projects: [{ id: 1, name: 'вднх' }],
            selected_lines: [],
            selected_targets: [],
            selected_geos: [],
            list_delivers: [
                {
                    id: 'вднх',
                    line: 'aut',
                    subline: 'подлиния 2',
                    segment: 'сегмент1',
                    geo: 'России',
                    format: 'Видео в посте',
                    tiz_post: 'Пройдите программу обучения руководителей по нацпроекту!',
                    is_important: 'Нет',
                    comment: 'Нет'
                }
            ],

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
.mt-15 {
    margin-top: 15px;
}

.btn_run_delivers {
    border-radius: 6px;
    background: var(--blue-500, #3B82F6);
    padding: 14px 16px 14px 16px;

    margin-left: 8px;

    cursor: pointer;
}

.text-orange {
    color: var(--red-500, #EF4444);
    text-align: center;

    /* Input/Medium Semi Bold */
    font-size: 15px;
    font-family: Inter;
    font-weight: 600;
    letter-spacing: 0.075px;
}

.h-46 {
    height: 46px;
}

.btn_create_more {
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 6px;
    background: var(--teal-500, #14B8A6);
    width: 16vw;
}

.btn_clear_list {
    border-radius: 6px;
    background: var(--red-100, #FEE2E2);
    display: flex;
    align-items: center;
    justify-content: center;
    width: 11vw;

    margin-left: 8px;
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

.article_selecter_warning {
    border-radius: 6px;
    border: 1px solid #F87171;
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    outline: none;

    padding: 14px 16px 14px 16px;
    /* width: 100%; */
}

.text_grey_16 {
    color: var(--gray-500, #6B7280);
    text-align: center;

    /* Base/Medium */
    font-size: 16px;
    font-family: Inter;
    font-weight: 500;
    line-height: 24px;
    letter-spacing: 0.08px;
}

.text-6 {
    color: var(--gray-500, #6B7280);

    /* XS/Medium */
    font-size: 12px;
    font-family: Inter;
    font-weight: 500;
    line-height: 16px;
    letter-spacing: 0.06px;
}

.cntr_close {
    border-radius: 999px;
    background: var(--gray-200, #E5E7EB);
    width: 15px;
    height: 15px;
    display: flex;
    justify-content: center;
    align-items: center;

    margin-left: 5px;
}

.cntr_item_project {
    border-radius: 999px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    display: flex;
    justify-content: center;
    align-items: center;
    height: 28px;
    padding-left: 6px;
    padding-right: 6px;
}

.cntr_tizer_rules {
    border-radius: 6px;
    background: #F3F4F6;
    padding: 20px;
    margin-top: 15px;
}

.text-5 {
    color: var(--gray-800, #1F2937);

    /* LG/Bold */
    font-size: 18px;
    font-family: Inter;
    font-weight: 700;
    letter-spacing: 0.09px;

    text-align: left;
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

.selecter_project {
    position: relative;
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);

    padding: 0px 8px 0px 8px;
    align-items: center;

    height: 44px;
}

.mt-12 {
    margin-top: 12px;
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

.text-grey_14 {
    color: var(--gray-800, #1F2937);
    /* Input/Small Semi Bold */
    font-size: 14px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.07px;
}

.text_3 {
    color: var(--gray-500, #6B7280);

    /* Input/Default Medium */
    font-size: 15px;
    font-family: Inter;
    font-weight: 500;
    letter-spacing: 0.075px;
}

.text_3_red {
    color: #F87171;

    /* Input/Default Medium */
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
}</style>