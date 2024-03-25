<template>
    <div class="net__modal_filters">

        <div class="modal_fltr_cntr_title">
            <div class="modal_accept__title">
                Фильтры
            </div>
        </div>

        <div class="modal_fltr_cntr_body">

            <!-- INTEREST -->
            <div class="modal_fltr_cntr_selecter">
                <div class="txt_filter_title">Тип сети</div>

            </div>

            <div>
                <div class="cntr_input_find_deliver">

                    <div class="input_find_deliver" placeholder="">
                    </div>
                    <svg @click="show_selecter_deliver = !show_selecter_deliver" class="svg_arrow_input" width="12"
                        height="12" viewBox="0 0 12 12" fill="none" xmlns="http://www.w3.org/2000/svg"
                        :class="{ rotate_180: show_selecter_deliver }">
                        <mask id="path-1-inside-1_634_29885" fill="white">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M1.23444 3.48444C1.26927 3.44952 1.31065 3.42181 1.35621 3.4029C1.40177 3.384 1.45061 3.37427 1.49994 3.37427C1.54926 3.37427 1.5981 3.384 1.64366 3.4029C1.68922 3.42181 1.7306 3.44952 1.76544 3.48444L5.99994 7.71969L10.2344 3.48444C10.2693 3.44957 10.3107 3.42191 10.3562 3.40305C10.4018 3.38418 10.4506 3.37446 10.4999 3.37446C10.5492 3.37446 10.5981 3.38418 10.6436 3.40305C10.6892 3.42191 10.7306 3.44957 10.7654 3.48444C10.8003 3.5193 10.828 3.5607 10.8468 3.60625C10.8657 3.6518 10.8754 3.70063 10.8754 3.74994C10.8754 3.79925 10.8657 3.84807 10.8468 3.89363C10.828 3.93918 10.8003 3.98057 10.7654 4.01544L6.26544 8.51544C6.2306 8.55036 6.18922 8.57807 6.14366 8.59697C6.0981 8.61588 6.04926 8.62561 5.99994 8.62561C5.95061 8.62561 5.90177 8.61588 5.85621 8.59697C5.81065 8.57807 5.76927 8.55036 5.73444 8.51544L1.23444 4.01544C1.19952 3.9806 1.17181 3.93922 1.1529 3.89366C1.134 3.8481 1.12427 3.79926 1.12427 3.74994C1.12427 3.70061 1.134 3.65177 1.1529 3.60621C1.17181 3.56065 1.19952 3.51927 1.23444 3.48444Z" />
                        </mask>
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M1.23444 3.48444C1.26927 3.44952 1.31065 3.42181 1.35621 3.4029C1.40177 3.384 1.45061 3.37427 1.49994 3.37427C1.54926 3.37427 1.5981 3.384 1.64366 3.4029C1.68922 3.42181 1.7306 3.44952 1.76544 3.48444L5.99994 7.71969L10.2344 3.48444C10.2693 3.44957 10.3107 3.42191 10.3562 3.40305C10.4018 3.38418 10.4506 3.37446 10.4999 3.37446C10.5492 3.37446 10.5981 3.38418 10.6436 3.40305C10.6892 3.42191 10.7306 3.44957 10.7654 3.48444C10.8003 3.5193 10.828 3.5607 10.8468 3.60625C10.8657 3.6518 10.8754 3.70063 10.8754 3.74994C10.8754 3.79925 10.8657 3.84807 10.8468 3.89363C10.828 3.93918 10.8003 3.98057 10.7654 4.01544L6.26544 8.51544C6.2306 8.55036 6.18922 8.57807 6.14366 8.59697C6.0981 8.61588 6.04926 8.62561 5.99994 8.62561C5.95061 8.62561 5.90177 8.61588 5.85621 8.59697C5.81065 8.57807 5.76927 8.55036 5.73444 8.51544L1.23444 4.01544C1.19952 3.9806 1.17181 3.93922 1.1529 3.89366C1.134 3.8481 1.12427 3.79926 1.12427 3.74994C1.12427 3.70061 1.134 3.65177 1.1529 3.60621C1.17181 3.56065 1.19952 3.51927 1.23444 3.48444Z"
                            fill="#1F2937" />
                        <path
                            d="M1.76544 3.48444L1.05744 4.19065L1.05827 4.19148L1.76544 3.48444ZM5.99994 7.71969L5.29277 8.42673L5.99994 9.13403L6.70711 8.42673L5.99994 7.71969ZM10.2344 3.48444L9.52733 2.77733L9.52727 2.77739L10.2344 3.48444ZM10.8754 3.74994H9.87541H10.8754ZM6.26544 8.51544L5.55833 7.80833L5.55744 7.80923L6.26544 8.51544ZM5.73444 8.51544L6.44244 7.80923L6.44154 7.80833L5.73444 8.51544ZM1.23444 4.01544L1.94155 3.30833L1.94065 3.30744L1.23444 4.01544ZM1.94244 4.19065C1.88438 4.24885 1.81541 4.29503 1.73948 4.32654L0.972946 2.47927C0.805895 2.54858 0.654163 2.65018 0.526438 2.77823L1.94244 4.19065ZM1.73948 4.32654C1.66354 4.35805 1.58214 4.37427 1.49994 4.37427V2.37427C1.31908 2.37427 1.14 2.40995 0.972946 2.47927L1.73948 4.32654ZM1.49994 4.37427C1.41773 4.37427 1.33633 4.35805 1.2604 4.32654L2.02693 2.47927C1.85988 2.40995 1.68079 2.37427 1.49994 2.37427V4.37427ZM1.2604 4.32654C1.18446 4.29503 1.11549 4.24885 1.05744 4.19065L2.47344 2.77823C2.34571 2.65018 2.19398 2.54858 2.02693 2.47927L1.2604 4.32654ZM1.05827 4.19148L5.29277 8.42673L6.70711 7.01264L2.47261 2.77739L1.05827 4.19148ZM6.70711 8.42673L10.9416 4.19148L9.52727 2.77739L5.29277 7.01264L6.70711 8.42673ZM10.9415 4.19154C10.8836 4.24954 10.8147 4.29554 10.7389 4.32692L9.97357 2.47917C9.80669 2.54829 9.65505 2.64961 9.52733 2.77733L10.9415 4.19154ZM10.7389 4.32692C10.6632 4.35831 10.582 4.37446 10.4999 4.37446V2.37446C10.3193 2.37446 10.1404 2.41004 9.97357 2.47917L10.7389 4.32692ZM10.4999 4.37446C10.4179 4.37446 10.3367 4.35831 10.2609 4.32692L11.0263 2.47917C10.8594 2.41004 10.6806 2.37446 10.4999 2.37446V4.37446ZM10.2609 4.32692C10.1852 4.29554 10.1163 4.24954 10.0583 4.19154L11.4725 2.77733C11.3448 2.64961 11.1932 2.54829 11.0263 2.47917L10.2609 4.32692ZM10.0583 4.19154C10.0003 4.13355 9.95434 4.06471 9.92295 3.98893L11.7707 3.22357C11.7016 3.05669 11.6003 2.90505 11.4725 2.77733L10.0583 4.19154ZM9.92295 3.98893C9.89156 3.91316 9.87541 3.83195 9.87541 3.74994H11.8754C11.8754 3.56931 11.8398 3.39045 11.7707 3.22357L9.92295 3.98893ZM9.87541 3.74994C9.87541 3.66793 9.89156 3.58672 9.92295 3.51094L11.7707 4.27631C11.8398 4.10942 11.8754 3.93056 11.8754 3.74994H9.87541ZM9.92295 3.51094C9.95434 3.43517 10.0003 3.36632 10.0583 3.30833L11.4725 4.72254C11.6003 4.59482 11.7016 4.44319 11.7707 4.27631L9.92295 3.51094ZM10.0583 3.30833L5.55833 7.80833L6.97254 9.22255L11.4725 4.72254L10.0583 3.30833ZM5.55744 7.80923C5.6155 7.75102 5.68447 7.70484 5.7604 7.67334L6.52693 9.52061C6.69397 9.45129 6.84571 9.3497 6.97344 9.22165L5.55744 7.80923ZM5.7604 7.67334C5.83633 7.64183 5.91773 7.62561 5.99994 7.62561V9.62561C6.1808 9.62561 6.35988 9.58993 6.52693 9.52061L5.7604 7.67334ZM5.99994 7.62561C6.08215 7.62561 6.16355 7.64183 6.23948 7.67334L5.47295 9.52061C5.63999 9.58993 5.81908 9.62561 5.99994 9.62561V7.62561ZM6.23948 7.67334C6.31541 7.70484 6.38438 7.75102 6.44244 7.80923L5.02644 9.22165C5.15417 9.3497 5.3059 9.45129 5.47295 9.52061L6.23948 7.67334ZM6.44154 7.80833L1.94154 3.30833L0.527331 4.72254L5.02733 9.22255L6.44154 7.80833ZM1.94065 3.30744C1.99885 3.36549 2.04503 3.43446 2.07654 3.5104L0.229266 4.27693C0.298584 4.44398 0.400177 4.59571 0.528225 4.72344L1.94065 3.30744ZM2.07654 3.5104C2.10805 3.58633 2.12427 3.66773 2.12427 3.74994H0.124268C0.124268 3.9308 0.159948 4.10988 0.229266 4.27693L2.07654 3.5104ZM2.12427 3.74994C2.12427 3.83215 2.10805 3.91355 2.07654 3.98948L0.229266 3.22295C0.159948 3.38999 0.124268 3.56908 0.124268 3.74994H2.12427ZM2.07654 3.98948C2.04503 4.06541 1.99885 4.13438 1.94065 4.19244L0.528225 2.77644C0.400177 2.90416 0.298584 3.0559 0.229266 3.22295L2.07654 3.98948Z"
                            fill="#1F2937" mask="url(#path-1-inside-1_634_29885)" />
                    </svg>
                    <selecter-interests v-show="show_selecter_deliver"
                        :interests="['Социальная сеть', 'Тизерная сеть', 'Банерная сеть', 'Нет']" />
                </div>
            </div>

            <div v-show="!is_all_selected">
                <div v-for="id in ['Социальная сеть', 'Тизерная сеть']" v-bind:key="id" class="selected_deliver">
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
    </div>
</template>

<script>



import SelecterInterests from './SelecterInterests.vue'
// import SelecterInterest from '../SelecterInterest.vue'

export default {
    data() {
        return {
            show_find_deliver: false,
            show_selecter_deliver: false,
            is_all_selected: false,
            show_find_behavior: false,
            show_selecter_interest_mt: false,
            is_all_geo_selected: false,
            show_find_interest: false,
            show_selecter_interest: false,
            is_all_interest_selected: false,
            is_male_selected: false,
            is_female_selected: false,


            show_find_interest_mt: false,
            show_selecter_behavior: false,
            show_find_behavior_vk: false,
            show_selecter_behavior_vk: false,
            show_find_interest_vk: false,
            show_selecter_interest_vk: false,
            show_find_dis_interest_vk: false,
            show_selecter_dis_interest_vk: false,
            show_find_interest_behavior: false,
            show_selecter_interest_behavior: false

        }
    },
    components: {
        'selecter-interests': SelecterInterests,
        // 'selecter-interest': SelecterInterest
    }
}

</script>

<style scoped>
.svg_arrow_input {
    cursor: pointer;
    position: absolute;
    right: 14px;
    top: 50%;
    transform: translateY(-50%);
}

.txt_filter_title {
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

.title_filter {
    width: 75%;
    text-align: left;
}

.select_all {
    color: var(--gray-800, #1F2937);
    font-family: Inter;
    font-size: 10px;
    font-style: normal;
    font-weight: 500;
    line-height: 20px;
    /* 200% */
    letter-spacing: 0.05px;
    text-align: left;
    padding-left: 14px;
    margin-top: 14px;
    cursor: pointer;
}

.selected_color {
    color: #3B82F6 !important
}

.rotate_180 {
    transform: rotate(180deg) translateY(50%);
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
    margin-top: 4px;
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
    height: 35px;
    padding: 7px 16px 7px 36px;
    box-sizing: border-box;
    outline: none;
}

.cntr_input_range_label {
    position: relative;
}

.cntr_input_range {
    position: relative;
    width: 180px;
    height: 5px
}

.input__range_min {
    position: absolute;
    top: 0;
    left: 0;
    width: 100px;
}

.input__range_max {

    width: 100px;
    position: absolute;
    top: 0;
    right: 0;
}

.input_range_label {
    position: absolute;
    top: 2px;
    left: 3px;
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

.modal_fltr_cntr_body {
    /* padding-left: 10px; */
    margin-top: 28px;
}

.modal_fltr_cntr_selecter {
    display: flex;
    align-items: center;
    width: 220px;
    justify-content: space-between;
    /* height: 40px; */
    /* cursor: pointer; */
    margin-top: 20px;
}

.modal_fltr_cntr_selecter_gender {
    display: flex;
    align-items: center;
    width: 192px;
    /* justify-content: space-between; */
    height: 30px;
}

.ml-30 {
    margin-left: 30px;
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
}

.cur_p {
    cursor: pointer
}


.net__modal_filters {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 19px 20px 0 20px;

    position: absolute;
    width: 260px;
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