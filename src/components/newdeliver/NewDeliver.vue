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

                <div v-show="!show_rules_tizer_create" class="text-1 mt-12">Новая доставка</div>

                <div v-show="!show_rules_tizer_create" class="line mt-10">
                </div>

                <div>
                    <div v-show="!show_rules_tizer_create" style="width: fit-content; margin-top: 15px" class="text-2">
                        Выберите проект
                    </div>

                    <div v-show="!show_rules_tizer_create" class="selecter_project row_between mt-10">
                        <div v-for="project in selected_projects" v-bind:key="project.id" class="cntr_item_project">
                            <div class="text-6">{{ project.name }}</div>
                            <div class="cntr_close">
                                <svg width="9" height="8" viewBox="0 0 9 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M7.42707 1.07345C7.45035 1.09667 7.46882 1.12426 7.48143 1.15463C7.49403 1.185 7.50052 1.21756 7.50052 1.25045C7.50052 1.28333 7.49403 1.31589 7.48143 1.34626C7.46882 1.37664 7.45035 1.40422 7.42707 1.42745L1.92707 6.92745C1.88013 6.97439 1.81646 7.00076 1.75007 7.00076C1.68368 7.00076 1.62001 6.97439 1.57307 6.92745C1.52613 6.8805 1.49976 6.81683 1.49976 6.75045C1.49976 6.68406 1.52613 6.62039 1.57307 6.57345L7.07307 1.07345C7.09629 1.05017 7.12388 1.03169 7.15425 1.01909C7.18463 1.00649 7.21719 1 7.25007 1C7.28296 1 7.31552 1.00649 7.34589 1.01909C7.37626 1.03169 7.40385 1.05017 7.42707 1.07345Z"
                                        fill="#6B7280" />
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M1.57296 1.07345C1.54968 1.09667 1.53121 1.12426 1.5186 1.15463C1.506 1.185 1.49951 1.21756 1.49951 1.25045C1.49951 1.28333 1.506 1.31589 1.5186 1.34626C1.53121 1.37664 1.54968 1.40422 1.57296 1.42745L7.07296 6.92745C7.1199 6.97439 7.18357 7.00076 7.24996 7.00076C7.31635 7.00076 7.38002 6.97439 7.42696 6.92745C7.4739 6.8805 7.50027 6.81683 7.50027 6.75045C7.50027 6.68406 7.4739 6.62039 7.42696 6.57345L1.92696 1.07345C1.90374 1.05017 1.87615 1.03169 1.84578 1.01909C1.8154 1.00649 1.78284 1 1.74996 1C1.71707 1 1.68451 1.00649 1.65414 1.01909C1.62377 1.03169 1.59618 1.05017 1.57296 1.07345Z"
                                        fill="#6B7280" />
                                </svg>

                            </div>
                        </div>

                        <div v-show="!selected_projects.length && !selecter_project_focus" class="text_3">Выбрать</div>

                        <input class="selecter_input text_3" v-show="selecter_project_focus" />

                        <div class="project_item" v-show="selecter_project_focus">вднх</div>

                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                fill="#6B7280" />
                        </svg>
                    </div>

                    <div v-show="!show_rules_tizer_create" style="display: flex; justify-content: space-between">
                        <div class="w-50p">
                            <div style="width: fit-content; margin-top: 15px" class="text-2">
                                Выберите линию
                            </div>

                            <div class="selecter_project row_between mt-10">
                                <div v-show="!selected_lines.length && !selecter_line_focus" class="text_3">Выбрать
                                </div>
                                <input class="selecter_input text_3" v-show="selecter_line_focus" />
                                <div class="project_item" v-show="selecter_line_focus">линия 1</div>
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16"
                                    fill="none">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                        fill="#6B7280" />
                                </svg>
                            </div>

                            <div class="btn_add_new_segment text-4">
                                Новая линия
                            </div>
                        </div>
                        <div style="width: 50%">
                            <div style="width: fit-content; margin-top: 15px" class="text-2">
                                Таргетинг
                            </div>

                            <div class="selecter_project row_between mt-10">
                                <div v-show="!selected_targets.length && !selecter_target_focus" class="text_3">Выбрать
                                </div>
                                <input class="selecter_input text_3" v-show="selecter_target_focus" />

                                <div class="cntr_list_targets" v-show="selecter_target_focus">
                                    <div v-for="target in targets_found" v-bind:key="target.id">
                                        <div class="target_item">
                                            {{ target.name }}
                                        </div>
                                    </div>
                                </div>


                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16"
                                    fill="none">
                                    <path fill-rule="evenodd" clip-rule="evenodd"
                                        d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                        fill="#6B7280" />
                                </svg>
                            </div>

                            <div class="btn_add_new_segment text-4">
                                Добавить новый сегмент
                            </div>
                        </div>
                    </div>



                    <div style="width: fit-content; margin-top: 15px" class="text-2">
                        Гео
                    </div>

                    <div class="selecter_project row_between mt-10">
                        <div v-show="!selected_geos.length && !selecter_geos_focus" class="text_3">Выбрать</div>
                        <input class="selecter_input text_3" v-show="selecter_geos_focus" />

                        <div class="project_item" v-show="selecter_geos_focus">Россия</div>

                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                fill="#6B7280" />
                        </svg>
                    </div>

                    <div style="width: fit-content; margin-top: 15px" class="text-2">
                        Месседж
                    </div>

                    <div class="mt-10">
                        <input style="width: calc(100% - 16px);" class="selecter_project selecter_input text_3 input_message" placeholder="Ввод" />
                    </div>

                    <div style="width: fit-content; margin-top: 15px" class="text-2">
                        Статья
                    </div>

                    <div class=" row_between mt-10" :class="{article_selecter_warning: true, selecter_project: false}">
                        <div :class="{text_3: false, text_3_red: true}">Выбрать</div>
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                                fill="#6B7280" />
                        </svg>
                    </div>

                    <div class="input_link_futter_warning">Пожалуйста, заполните поле «Статья»</div>

                    <div v-show="show_rules_tizer_create" class="cntr_tizer_rules">
                        <div class="text-5">Правила создания тизера</div>

                        <div class="rules_text">
                            <div v-for="rule in rules" v-bind:key="rule.id" style="display: flex">
                                &#x2022; <div style="margin-left: 5px">{{ rule.name }}</div>
                            </div>
                        </div>
                    </div>


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
}
</style>