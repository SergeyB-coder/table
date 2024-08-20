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
                <div class="txt_filter_title">ID</div>
            </div>

            <div>
                <div class="cntr-row"
                    style="height: 35px !important; margin-top: 12px; box-sizing: border-box; width: 210px;">

                    <input placeholder="" class="input_add_export_segments txt_input_delivers mon_seg_add_exp_part1"
                        style="height: 35px !important;" />
                    <div style="height: 35px !important;" @click="notifyParent"
                        class="input_reports txt_input_filters mon_seg_add_exp_part2">
                        Списком
                    </div>
                </div>
            </div>

            <div class="modal_fltr_cntr_selecter">
                <div class="txt_filter_title">Сеть</div>
            </div>

            <div>
                <div class="cntr_input_filter_monitoring">

                    <div class="input_date_start date_start" style="text-align: left; padding-left: 16px; height: 35px">

                    </div>
                    <svg :class="{ rotate_180: show_selecter_net }" @click="show_selecter_net = !show_selecter_net"
                        class="svg_arrow_input" width="14" height="15" viewBox="0 0 14 15" fill="none"
                        xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M1.44103 4.56506C1.48167 4.52431 1.52995 4.49199 1.5831 4.46993C1.63625 4.44788 1.69324 4.43652 1.75078 4.43652C1.80833 4.43652 1.86531 4.44788 1.91846 4.46993C1.97161 4.49199 2.01989 4.52431 2.06053 4.56506L7.00078 9.50618L11.941 4.56506C11.9817 4.52438 12.03 4.49211 12.0831 4.4701C12.1363 4.44808 12.1933 4.43675 12.2508 4.43675C12.3083 4.43675 12.3653 4.44808 12.4184 4.4701C12.4716 4.49211 12.5199 4.52438 12.5605 4.56506C12.6012 4.60573 12.6335 4.65402 12.6555 4.70717C12.6775 4.76032 12.6888 4.81728 12.6888 4.87481C12.6888 4.93233 12.6775 4.98929 12.6555 5.04244C12.6335 5.09559 12.6012 5.14388 12.5605 5.18456L7.31053 10.4346C7.26989 10.4753 7.22161 10.5076 7.16846 10.5297C7.11531 10.5517 7.05833 10.5631 7.00078 10.5631C6.94324 10.5631 6.88625 10.5517 6.8331 10.5297C6.77995 10.5076 6.73167 10.4753 6.69103 10.4346L1.44103 5.18456C1.40029 5.14392 1.36796 5.09564 1.34591 5.04248C1.32385 4.98933 1.3125 4.93235 1.3125 4.87481C1.3125 4.81726 1.32385 4.76028 1.34591 4.70713C1.36796 4.65397 1.40029 4.6057 1.44103 4.56506Z"
                            fill="#374151" />
                    </svg>


                    <selecter-interest v-show="show_selecter_net"
                        :interests="['Социальная сеть', 'Тизерная сеть', 'Банерная сеть', 'Нет']" />
                </div>
            </div>

            <div v-for="id in ['сеть0', 'сеть1']" v-bind:key="id" class="selected_deliver">
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

            <div class="modal_fltr_cntr_selecter">
                <div class="txt_filter_title">Формат</div>
            </div>

            <div style="height: 35px;">
                <div class="cntr_input_filter_monitoring">

                    <div class="input_date_start date_start"
                        style="text-align: left; padding-left: 16px; height: 35px;">

                    </div>
                    <svg :class="{ rotate_180: show_selecter_deliver }"
                        @click="show_selecter_deliver = !show_selecter_deliver" class="svg_arrow_input" width="14"
                        height="15" viewBox="0 0 14 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path fill-rule="evenodd" clip-rule="evenodd"
                            d="M1.44103 4.56506C1.48167 4.52431 1.52995 4.49199 1.5831 4.46993C1.63625 4.44788 1.69324 4.43652 1.75078 4.43652C1.80833 4.43652 1.86531 4.44788 1.91846 4.46993C1.97161 4.49199 2.01989 4.52431 2.06053 4.56506L7.00078 9.50618L11.941 4.56506C11.9817 4.52438 12.03 4.49211 12.0831 4.4701C12.1363 4.44808 12.1933 4.43675 12.2508 4.43675C12.3083 4.43675 12.3653 4.44808 12.4184 4.4701C12.4716 4.49211 12.5199 4.52438 12.5605 4.56506C12.6012 4.60573 12.6335 4.65402 12.6555 4.70717C12.6775 4.76032 12.6888 4.81728 12.6888 4.87481C12.6888 4.93233 12.6775 4.98929 12.6555 5.04244C12.6335 5.09559 12.6012 5.14388 12.5605 5.18456L7.31053 10.4346C7.26989 10.4753 7.22161 10.5076 7.16846 10.5297C7.11531 10.5517 7.05833 10.5631 7.00078 10.5631C6.94324 10.5631 6.88625 10.5517 6.8331 10.5297C6.77995 10.5076 6.73167 10.4753 6.69103 10.4346L1.44103 5.18456C1.40029 5.14392 1.36796 5.09564 1.34591 5.04248C1.32385 4.98933 1.3125 4.93235 1.3125 4.87481C1.3125 4.81726 1.32385 4.76028 1.34591 4.70713C1.36796 4.65397 1.40029 4.6057 1.44103 4.56506Z"
                            fill="#374151" />
                    </svg>


                    <selecter-interest v-show="show_selecter_deliver"
                        :interests="['Формат 1', 'Формат 2', 'Формат 3', 'Формат 4']" />
                </div>
            </div>

            <div v-for="id in ['Формат0']" v-bind:key="id" class="selected_deliver">
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

            <div class="modal_fltr_cntr_selecter">
                <div class="txt_filter_title">Наличие ошибки</div>
            </div>
            <div class="cntr-row" style="gap: 8px">
                <div style="height: 24px; box-sizing: border-box;" class="selected_deliver" @click="select_all = !select_all" :class="{bg_blue_color: select_all}">
                    <div class="text__settings_deliver_sm" :class="{white_color: select_all}">Все</div>
                </div>
                <div class="selected_deliver">
                    <div class="text__settings_deliver_sm">Да</div>
                </div>
                <div class="selected_deliver">
                    <div class="text__settings_deliver_sm">Нет</div>
                </div>
            </div>


        </div>
    </div>
</template>

<script>



import SelecterInterests from './SelecterInterests.vue'
// import SelecterInterest from '../SelecterInterest.vue'
// import SelecterStatus from './SelecterStatus.vue';

export default {
    props: ['show_segments_list_id'],
    data() {
        return {
            select_all: false,
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
            show_selecter_interest_behavior: false,

            show_selecter_net: false

        }
    },
    components: {
        // 'selecter-status': SelecterStatus,
        'selecter-interest': SelecterInterests,
    },
    methods: {
        notifyParent() {
            this.$emit('toggle-segments-list');
        }
    }
}

</script>

<style scoped>
.bg_blue_color {
    background-color: #3B82F6 !important;
}
.white_color {
    
    color: #FFF !important;
}
.mon_seg_add_exp_part2 {
    flex: 1;
    border-top-left-radius: 0 !important;
    /* Оставляем левые углы острыми */
    border-bottom-left-radius: 0 !important;
    align-items: center;
    display: flex;
    cursor: pointer;
    justify-content: center;
    /* transition: background-color 1s ease; */
}

.mon_seg_add_exp_part2:hover {
    background: transparent !important;
}

.mon_seg_add_exp_part2:active {
    background-color: #3B82F6 !important;
    color: #fff !important;
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

.txt_input_filters {
    font-family: Inter;
    font-size: 12px;
    font-weight: 500;
    line-height: 13.07px;
    letter-spacing: 0.005em;
    text-align: left;
    color: #1F2937
}

.input_reports {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;
    color: #6B7280 !important;
    padding-left: 16px;
    padding-right: 16px;
}

.input_add_export {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;

    padding-left: 20px;
    color: #6B7280 !important
}

.input_add_export:hover {
    background: #F3F4F6;
}

.input_add_export:focus {
    background: #F3F4F6;
}

.mon_seg_add_exp_part1 {
    flex: 4;
    border-top-right-radius: 0 !important;
    /* Оставляем правые углы острыми */
    border-bottom-right-radius: 0 !important;
}

.txt_input_delivers {
    font-family: Inter;
    font-size: 14px;
    font-weight: 500;
    line-height: 16px;
    letter-spacing: 0.005em;
    text-align: left;
    color: #1F2937
}

.input_add_export_segments {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;

    padding-left: 20px;
    color: #1F2937 !important
}

.input_add_export_segments:focus {
    background-color: white !important;
}

.cntr-row {
    display: flex;
    position: relative;
}

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
    align-items: center;
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

.cntr_input_filter_monitoring {
    margin-top: 12px;
    position: relative;
    width: 210px;
}

.input_date_start {
    border-radius: 6px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: var(--white-white, #FFF);

    /* Drop Shadow/sm */
    box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.05);
    width: 100%;
    /* height: 35px; */
    padding: 12px;
    box-sizing: border-box;
    outline: none;

    font-family: Inter;
    font-size: 10px;
    font-weight: 500;
    line-height: 13.07px;
    letter-spacing: 0.005em;
    text-align: left;
    color: #6B7280
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