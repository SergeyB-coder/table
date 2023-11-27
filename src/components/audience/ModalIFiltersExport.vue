<template>
    <div class="settings__modal_filters">

        <div class="modal_fltr_cntr_title">
            <div class="modal_accept__title">
                Фильтры
            </div>
        </div>

        <div class="modal_fltr_cntr_body">


            <div @click="show_find_geo = !show_find_geo" class="modal_fltr_cntr_selecter">
                <div>ID</div>
            </div>
            <div>
                <div class="cntr_input_find_deliver">
                    <svg class="find_svg" width="10" height="11" viewBox="0 0 10 11" fill="none"
                        xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M4.58333 8.41667C6.42428 8.41667 7.91667 6.92428 7.91667 5.08333C7.91667 3.24238 6.42428 1.75 4.58333 1.75C2.74238 1.75 1.25 3.24238 1.25 5.08333C1.25 6.92428 2.74238 8.41667 4.58333 8.41667Z"
                            stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        <path d="M8.75 9.25L6.9375 7.4375" stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round"
                            stroke-linejoin="round" />
                    </svg>

                    <input class="input_find_deliver" placeholder="Поиск" @focus="show_selecter_id = true"
                        @focusout="show_selecter_id = false" />
                    <selecter-id v-show="show_selecter_id" />
                </div>

                <div v-show="!is_all_selected">
                    <div v-for="id in ['Рур', 'Дос']" v-bind:key="id" class="selected_deliver">
                        <div class="text__settings_deliver_sm">{{ id }}</div>
                        <svg class="ml-10" width="10" height="10" viewBox="0 0 10 10" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M4.99967 9.47908C2.52884 9.47908 0.520508 7.47075 0.520508 4.99992C0.520508 2.52909 2.52884 0.520752 4.99967 0.520752C7.47051 0.520752 9.47884 2.52909 9.47884 4.99992C9.47884 7.47075 7.47051 9.47908 4.99967 9.47908ZM4.99967 1.14575C2.87467 1.14575 1.14551 2.87492 1.14551 4.99992C1.14551 7.12492 2.87467 8.85408 4.99967 8.85408C7.12467 8.85408 8.85384 7.12492 8.85384 4.99992C8.85384 2.87492 7.12467 1.14575 4.99967 1.14575Z"
                                fill="#6B7280" />
                            <path
                                d="M3.82122 6.49157C3.74206 6.49157 3.66289 6.4624 3.60039 6.3999C3.47956 6.27907 3.47956 6.07907 3.60039 5.95824L5.95872 3.5999C6.07956 3.47907 6.27956 3.47907 6.40039 3.5999C6.52122 3.72074 6.52122 3.92074 6.40039 4.04157L4.04206 6.3999C3.98372 6.4624 3.90039 6.49157 3.82122 6.49157Z"
                                fill="#6B7280" />
                            <path
                                d="M6.17956 6.49157C6.10039 6.49157 6.02122 6.4624 5.95872 6.3999L3.60039 4.04157C3.47956 3.92074 3.47956 3.72074 3.60039 3.5999C3.72122 3.47907 3.92122 3.47907 4.04206 3.5999L6.40039 5.95824C6.52122 6.07907 6.52122 6.27907 6.40039 6.3999C6.33789 6.4624 6.25872 6.49157 6.17956 6.49157Z"
                                fill="#6B7280" />
                        </svg>
                    </div>
                </div>
            </div>

            <div class="modal_fltr_cntr_selecter">
                <div>Название</div>
            </div>
            <div>
                <div class="cntr_input_find_deliver">
                    <svg class="find_svg" width="10" height="11" viewBox="0 0 10 11" fill="none"
                        xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M4.58333 8.41667C6.42428 8.41667 7.91667 6.92428 7.91667 5.08333C7.91667 3.24238 6.42428 1.75 4.58333 1.75C2.74238 1.75 1.25 3.24238 1.25 5.08333C1.25 6.92428 2.74238 8.41667 4.58333 8.41667Z"
                            stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        <path d="M8.75 9.25L6.9375 7.4375" stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round"
                            stroke-linejoin="round" />
                    </svg>

                    <input class="input_find_deliver" placeholder="Поиск" @focus="show_selecter_name = true"
                        @focusout="show_selecter_name = false" />
                    <selecter-id v-show="show_selecter_name" />
                </div>

                <div v-show="!is_all_selected">
                    <div v-for="id in ['Клик', 'Кдак']" v-bind:key="id" class="selected_deliver">
                        <div class="text__settings_deliver_sm">{{ id }}</div>
                        <svg class="ml-10" width="10" height="10" viewBox="0 0 10 10" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M4.99967 9.47908C2.52884 9.47908 0.520508 7.47075 0.520508 4.99992C0.520508 2.52909 2.52884 0.520752 4.99967 0.520752C7.47051 0.520752 9.47884 2.52909 9.47884 4.99992C9.47884 7.47075 7.47051 9.47908 4.99967 9.47908ZM4.99967 1.14575C2.87467 1.14575 1.14551 2.87492 1.14551 4.99992C1.14551 7.12492 2.87467 8.85408 4.99967 8.85408C7.12467 8.85408 8.85384 7.12492 8.85384 4.99992C8.85384 2.87492 7.12467 1.14575 4.99967 1.14575Z"
                                fill="#6B7280" />
                            <path
                                d="M3.82122 6.49157C3.74206 6.49157 3.66289 6.4624 3.60039 6.3999C3.47956 6.27907 3.47956 6.07907 3.60039 5.95824L5.95872 3.5999C6.07956 3.47907 6.27956 3.47907 6.40039 3.5999C6.52122 3.72074 6.52122 3.92074 6.40039 4.04157L4.04206 6.3999C3.98372 6.4624 3.90039 6.49157 3.82122 6.49157Z"
                                fill="#6B7280" />
                            <path
                                d="M6.17956 6.49157C6.10039 6.49157 6.02122 6.4624 5.95872 6.3999L3.60039 4.04157C3.47956 3.92074 3.47956 3.72074 3.60039 3.5999C3.72122 3.47907 3.92122 3.47907 4.04206 3.5999L6.40039 5.95824C6.52122 6.07907 6.52122 6.27907 6.40039 6.3999C6.33789 6.4624 6.25872 6.49157 6.17956 6.49157Z"
                                fill="#6B7280" />
                        </svg>
                    </div>
                </div>
            </div>

            <div class="modal_fltr_cntr_selecter">
                <div>Статус</div>
            </div>
            <div class="modal_fltr_cntr_selecter_gender">
                <div 
                    :class="{ selected_color: false }" 
                    class="text__settings_deliver_sm cur_p"
                >
                    Все
                </div>
                <div 
                    :class="{ selected_color: false }" 
                    class="text__settings_deliver_sm cur_p ml-11"
                >
                    Ошибка
                </div>
                <div 
                    :class="{ selected_color: false }" 
                    class="text__settings_deliver_sm cur_p ml-11"
                >
                    Выполнено
                </div>
                <div 
                    :class="{ selected_color: true }" 
                    class="text__settings_deliver_sm cur_p ml-11"
                >
                    В процессе
                </div>
            </div>

            <div class="modal_fltr_cntr_selecter">
                <div>Сеть</div>
            </div>
            <div class="modal_fltr_cntr_selecter_gender">
                <div 
                    :class="{ selected_color: false }" 
                    class="text__settings_deliver_sm cur_p"
                >
                    ВК
                </div>
                <div 
                    :class="{ selected_color: false }" 
                    class="text__settings_deliver_sm cur_p ml-11"
                >
                    ВКР
                </div>
                <div 
                    :class="{ selected_color: false }" 
                    class="text__settings_deliver_sm cur_p ml-11"
                >
                    МТ
                </div>
            </div>


            <!-- calendar -->
            <div @click="show_find_geo = !show_find_geo" class="modal_fltr_cntr_selecter">
                <div>Дата загрузки</div>
            </div>

            <div class="selecter_calendar">
                <svg width="11" height="12" viewBox="0 0 11 12" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <g clip-path="url(#clip0_604_21921)">
                        <path d="M7.66683 4.99984L8.3335 4.99984L8.3335 5.6665H7.66683V4.99984Z" fill="#1F2937"
                            stroke="#6B7280" stroke-width="0.666667" />
                        <path
                            d="M2.33333 0.666504C2.42174 0.666504 2.50652 0.701623 2.56904 0.764135C2.63155 0.826647 2.66667 0.911432 2.66667 0.999837V1.33317H8V0.999837C8 0.911432 8.03512 0.826647 8.09763 0.764135C8.16014 0.701623 8.24493 0.666504 8.33333 0.666504C8.42174 0.666504 8.50652 0.701623 8.56904 0.764135C8.63155 0.826647 8.66667 0.911432 8.66667 0.999837V1.33317H9.33333C9.68696 1.33317 10.0261 1.47365 10.2761 1.72369C10.5262 1.97374 10.6667 2.31288 10.6667 2.6665V9.99984C10.6667 10.3535 10.5262 10.6926 10.2761 10.9426C10.0261 11.1927 9.68696 11.3332 9.33333 11.3332H1.33333C0.979711 11.3332 0.640573 11.1927 0.390524 10.9426C0.140476 10.6926 0 10.3535 0 9.99984V2.6665C0 2.31288 0.140476 1.97374 0.390524 1.72369C0.640573 1.47365 0.979711 1.33317 1.33333 1.33317H2V0.999837C2 0.911432 2.03512 0.826647 2.09763 0.764135C2.16014 0.701623 2.24493 0.666504 2.33333 0.666504V0.666504ZM0.666667 3.33317V9.99984C0.666667 10.1766 0.736905 10.3462 0.861929 10.4712C0.986953 10.5963 1.15652 10.6665 1.33333 10.6665H9.33333C9.51014 10.6665 9.67971 10.5963 9.80474 10.4712C9.92976 10.3462 10 10.1766 10 9.99984V3.33317H0.666667Z"
                            fill="#1F2937" />
                    </g>
                    <defs>
                        <clipPath id="clip0_604_21921">
                            <rect width="10.6667" height="10.6667" fill="white" transform="translate(0 0.666504)" />
                        </clipPath>
                    </defs>
                </svg>

                <div class="text__settings_deliver_sm ml-16">
                    10.03.2023 - 07.04.2023
                </div>

                <svg :class="{ rotate_180: show_calendar }" @click="show_calendar = !show_calendar"
                    class="td__svg_arrow cur-pointer ml-10" width="16" height="16" viewBox="0 0 16 16" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                        d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                        fill="#6B7280" />
                </svg>

            </div>


        </div>
    </div>
</template>

<script>


import SelecterID from './SelecterID.vue'

export default {
    props: ['show_modal_is_save'],
    data() {
        return {
            show_find_deliver: false,

            show_selecter_id: false,
            show_selecter_name: false,

            is_all_selected: false,
            show_find_geo: false,
            show_selecter_geo: false,
            is_all_geo_selected: false,
            show_find_interest: false,
            show_selecter_interest: false,
            is_all_interest_selected: false,
            is_male_selected: false,
            is_female_selected: false,
            show_calendar: false
        }
    },
    components: {
        'selecter-id': SelecterID,
    }
}

</script>

<style scoped>

.selected_color {
    color: #3B82F6 !important
}
.ml-11 {
    margin-left: 11px;
}
.modal_fltr_cntr_selecter_gender {
    display: flex;
    align-items: center;
    width: 192px;
    /* justify-content: space-between; */
    height: 30px;
}

.rotate_180 {
    transform: rotate(180deg) ;
}

.selecter_calendar {
    border-radius: 8px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 210px;
    height: 40px;

    display: flex;
    align-items: center;

    padding-left: 16px;
    box-sizing: border-box;
}

.selected_deliver {
    margin-top: 10px;
    display: flex;
    padding: 4px 14px;
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    width: fit-content;
    cursor: pointer;
}

.selected_deliver:hover {
    background: #F3F4F6;
}

input::placeholder {
    color: var(--gray-500, #6B7280);
    font-family: Inter;
    font-size: 10px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px;
    /* 160% */
    letter-spacing: 0.05px;
}

.find_svg {
    position: absolute;
    top: 50%;
    left: 16px;
    transform: translateY(-50%);
}

.cntr_input_find_deliver {
    position: relative;
    width: 210px;
}

.input_find_deliver {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    width: 100%;
    padding: 14px 16px 14px 36px;
    box-sizing: border-box;
    outline: none;
}

input[type="range"] {
    -webkit-appearance: none;
    /* margin-right: 15px; */
    /* width: 15.6vw; */
    height: 4px;
    /* background: rgba(255, 255, 255, 0.6); */
    /* border-radius: 5px; */
    border-radius: 999px;
    background: var(--gray-200, #E5E7EB);
    background-image: linear-gradient(#3B82F6, #3B82F6);

    background-size: 70% 100%;
    background-repeat: no-repeat;
}

/* Input Thumb */
input[type="range"]::-webkit-slider-thumb {
    border: 3px solid #FFFFFF;
    margin-top: -2px;
    -webkit-appearance: none;
    height: 13px;
    width: 13px;
    border-radius: 50%;
    background: #FFFFFF;
    cursor: ew-resize;
    box-shadow: 0 0 2px 0 #555;
    transition: background .3s ease-in-out;
}

input[type="range"]::-moz-range-thumb {
    -webkit-appearance: none;
    height: 10px;
    width: 10px;
    border-radius: 50%;
    background: #FFFFFF;
    cursor: ew-resize;
    box-shadow: 0 0 2px 0 #555;
    transition: background .3s ease-in-out;
}

input[type="range"]::-ms-thumb {
    -webkit-appearance: none;
    height: 20px;
    width: 20px;
    border-radius: 50%;
    background: #FFFFFF;
    cursor: pointer;
    box-shadow: 0 0 2px 0 #555;
    transition: background .3s ease-in-out;
}

input[type="range"]::-webkit-slider-thumb:hover {
    background: #FFFFFF;
}

input[type="range"]::-moz-range-thumb:hover {
    background: #FFFFFF;
}

input[type="range"]::-ms-thumb:hover {
    background: #FFFFFF;
}

/* Input Track */
input[type=range]::-webkit-slider-runnable-track {
    -webkit-appearance: none;
    box-shadow: none;
    border: none;
    background: transparent;
}

input[type=range]::-moz-range-track {
    -webkit-appearance: none;
    box-shadow: none;
    border: none;
    background: transparent;
}

input[type="range"]::-ms-track {
    -webkit-appearance: none;
    box-shadow: none;
    border: none;
    background: transparent;
}

.ml-10 {
    margin-left: 10px;
}

.ml-16 {
    margin-left: 16px;
}

.modal_fltr_cntr_body {
    padding-left: 14px;
    margin-top: 28px;
}

.modal_fltr_cntr_selecter {
    display: flex;
    align-items: center;
    width: 210px;
    justify-content: space-between;
    height: 40px;
    cursor: pointer;
}

.modal_fltr_cntr_title {
    display: flex;
    width: 100%;
    justify-content: left;
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

.text__settings_deliver_sm {
    color: #6B7280;
    font-family: Inter;
    font-size: 10px;
    font-style: normal;
    font-weight: 500;
    line-height: 11px;
    /* 110% */
    letter-spacing: 0.05px;

    white-space: nowrap;
}

.cur_p {
    cursor: pointer
}


.settings__modal_filters {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 19px 20px 0 20px;

    position: absolute;
    width: 24vw;
    height: 100vh;
    right: 0;
    top: 0;

    /* White/White */

    background: #F9FAFB;
    /* Drop Shadow/xl */

    box-sizing: border-box;
    /* border-radius: 16px; */
    z-index: 13;
}
</style>