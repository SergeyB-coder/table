<template>
    <div class="cntr_modal_new_segment">

        <label class="input_label txt_label">Сегмент</label>
        <input class="input_segment txt_input" />

        <div class="cntr-row a-c mt-17">
            <div @click="is_check_connect = !is_check_connect" class="check_connect">
                <svg class="check_connect_tick" v-show="is_check_connect" width="13" height="10" viewBox="0 0 13 10" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M4.72188 9.45938C4.47188 9.45938 4.23438 9.35938 4.05938 9.18437L0.521875 5.64687C0.159375 5.28437 0.159375 4.68438 0.521875 4.32188C0.884375 3.95938 1.48437 3.95938 1.84687 4.32188L4.72188 7.19688L11.1469 0.771875C11.5094 0.409375 12.1094 0.409375 12.4719 0.771875C12.8344 1.13437 12.8344 1.73437 12.4719 2.09687L5.38438 9.18437C5.20937 9.35938 4.97188 9.45938 4.72188 9.45938Z"
                        fill="#6B7280" />
                </svg>
            </div>
            <label class="txt_label ml-12">Связать с имеющимся сегментом</label>
        </div>

        <label v-show="is_check_connect" class="input_label txt_label mt-13">Сегмент для связи с новым</label>
        <div v-show="is_check_connect" class="p-r">
            <input :class="{ input_active_bg: input_segment_connect_bg_active }" class="input_segment_pars txt_input" placeholder="-" />
            <svg @click="show_segment_connect_select_item = true" 
                @mouseleave="input_segment_connect_bg_active = false" 
                @mouseenter="input_segment_connect_bg_active = true"
                class="input__svg_arrow" width="16" height="16" viewBox="0 0 16 16" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                    fill="#6B7280" />
            </svg>

            <div @click="show_segment_connect_select_item = false" v-show="show_segment_connect_select_item" class="selected_item">
                <label class="txt_select_item">Все</label>
            </div>
        </div>

        <label class="input_label txt_label mt-13">ГЕО</label>
        <div class="p-r">
            <input :class="{ input_active_bg: input_bg_active, wrong_data: is_wrong_data }" class="input_segment_pars txt_input" placeholder="-" />
            <svg @click="show_select_item = true" @mouseleave="input_bg_active = false" @mouseenter="input_bg_active = true"
                class="input__svg_arrow" width="16" height="16" viewBox="0 0 16 16" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                    fill="#6B7280" />
            </svg>

            <div @click="show_select_item = false" v-show="show_select_item" class="selected_item">
                <label class="txt_select_item">Все</label>
            </div>
        </div>


        <label class="input_label txt_label mt-13">Исключенное ГЕО</label>
        <div class="p-r">
            <input :class="{ input_active_bg: input_dis_geo_active_bg }" class="input_segment_pars txt_input"
                placeholder="-" />
            <svg @click="show_select_item_dis_geo = true" @mouseleave="input_dis_geo_active_bg = false"
                @mouseenter="input_dis_geo_active_bg = true" class="input__svg_arrow" width="16" height="16"
                viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                    fill="#6B7280" />
            </svg>

            <div @click="show_select_item_dis_geo = false" v-show="show_select_item_dis_geo" class="selected_item">
                <label class="txt_select_item">Все</label>
            </div>
        </div>

        <label class="input_label txt_label mt-13">Возраст</label>
        <div class="p-r">
            <input :class="{ input_active_bg: input_age_active_bg }" class="input_segment_pars" placeholder="-" />
            <svg :class="{ rotate_180: show_config_age }" @click="show_config_age = !show_config_age"
                @mouseleave="input_age_active_bg = false" @mouseenter="input_age_active_bg = true" class="input__svg_arrow"
                width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                    fill="#6B7280" />
            </svg>

            <div v-show="show_config_age" class="cntr_config_age">
                <div class="cntr_input_range_label_min">
                    <label class="input_range_label txt_range_age">25</label>
                    <svg width="30" height="22" viewBox="0 0 30 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M0 2C0 0.895431 0.895431 0 2 0H28C29.1046 0 30 0.895431 30 2V17C30 18.1046 29.1046 19 28 19H19.7515C19.267 19 18.799 19.1758 18.4345 19.4948L16.317 21.3476C15.563 22.0074 14.437 22.0074 13.683 21.3476L11.5655 19.4948C11.201 19.1758 10.733 19 10.2485 19H2C0.895431 19 0 18.1046 0 17V2Z"
                            fill="white" />
                    </svg>
                </div>
                <div class="cntr_input_range_label_max">
                    <label class="input_range_label txt_range_age">55</label>
                    <svg width="30" height="22" viewBox="0 0 30 22" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path
                            d="M0 2C0 0.895431 0.895431 0 2 0H28C29.1046 0 30 0.895431 30 2V17C30 18.1046 29.1046 19 28 19H19.7515C19.267 19 18.799 19.1758 18.4345 19.4948L16.317 21.3476C15.563 22.0074 14.437 22.0074 13.683 21.3476L11.5655 19.4948C11.201 19.1758 10.733 19 10.2485 19H2C0.895431 19 0 18.1046 0 17V2Z"
                            fill="white" />
                    </svg>
                </div>
                <div class="cntr_input_range">
                    <input class="input__range_max" id="range" type="range" min="20" max="60" value="35" />
                    <input class="input__range_min rotate_180" id="range" type="range" min="20" max="60" value="35" />
                </div>
            </div>
        </div>

        <label class="input_label txt_label mt-13">Пол</label>
        <div class="p-r">
            <input :class="{ input_active_bg: input_gender_active_bg }" class="input_segment_pars" placeholder="-" />

            <svg :class="{ rotate_180: show_select_item_gender }"
                @click="show_select_item_gender = !show_select_item_gender" @mouseleave="input_gender_active_bg = false"
                @mouseenter="input_gender_active_bg = true" class="input__svg_arrow" width="16" height="16"
                viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                    fill="#6B7280" />
            </svg>


        </div>
        <div v-show="show_select_item_gender" class="selected_gender_item box_select">
            <div v-for="gender in ['Мужской', 'Женский', 'Все']" v-bind:key="gender" class="cntr_select_item">
                <label @click="selected_gender = gender" class="txt_select_item cur-pointer"
                    :class="{ selected_color: selected_gender === gender }">{{ gender }}</label>
            </div>
        </div>

        <!-- interest -->
        <label class="input_label txt_label mt-13">Интересы</label>
        <div class="p-r">
            <input :class="{ input_active_bg: input_interest_active_bg }" class="input_segment_pars txt_input"
                placeholder="-" />
            <svg @click="show_select_item_interest = !show_select_item_interest"
                @mouseleave="input_interest_active_bg = false" @mouseenter="input_interest_active_bg = true"
                class="input__svg_arrow" width="16" height="16" :class="{ rotate_180: show_select_item_interest }"
                viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                    d="M1.64592 4.64592C1.69236 4.59935 1.74754 4.56241 1.80828 4.5372C1.86903 4.512 1.93415 4.49902 1.99992 4.49902C2.06568 4.49902 2.13081 4.512 2.19155 4.5372C2.2523 4.56241 2.30747 4.59935 2.35392 4.64592L7.99992 10.2929L13.6459 4.64592C13.6924 4.59943 13.7476 4.56255 13.8083 4.53739C13.8691 4.51223 13.9342 4.49929 13.9999 4.49929C14.0657 4.49929 14.1308 4.51223 14.1915 4.53739C14.2522 4.56255 14.3074 4.59943 14.3539 4.64592C14.4004 4.6924 14.4373 4.74759 14.4624 4.80833C14.4876 4.86907 14.5005 4.93417 14.5005 4.99992C14.5005 5.06566 14.4876 5.13076 14.4624 5.1915C14.4373 5.25224 14.4004 5.30743 14.3539 5.35392L8.35392 11.3539C8.30747 11.4005 8.2523 11.4374 8.19155 11.4626C8.13081 11.4878 8.06568 11.5008 7.99992 11.5008C7.93415 11.5008 7.86903 11.4878 7.80828 11.4626C7.74754 11.4374 7.69236 11.4005 7.64592 11.3539L1.64592 5.35392C1.59935 5.30747 1.56241 5.2523 1.5372 5.19155C1.512 5.13081 1.49902 5.06568 1.49902 4.99992C1.49902 4.93415 1.512 4.86903 1.5372 4.80828C1.56241 4.74754 1.59935 4.69236 1.64592 4.64592Z"
                    fill="#6B7280" />
            </svg>

            <div @click="show_select_item_interest = false" v-show="show_select_item_interest" class="selected_item">
                <label class="txt_select_item">Все</label>
            </div>
        </div>

        <div class="cntr-row j-e mt-7 mb-8">


            <!-- save bnt -->
            <div class="grey-box cntr-row a-c btn_save p-r cur-pointer h-40">
                <svg width="17" height="17" viewBox="0 0 17 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <g clip-path="url(#clip0_422_57362)">
                        <path
                            d="M15.483 7.41408V8.02742C15.4822 9.46503 15.0167 10.8639 14.1559 12.0153C13.2951 13.1667 12.0852 14.0091 10.7066 14.4167C9.32795 14.8243 7.8545 14.7754 6.50597 14.2771C5.15745 13.7789 4.00609 12.8581 3.22363 11.6521C2.44117 10.4461 2.06952 9.01946 2.16411 7.58496C2.2587 6.15046 2.81446 4.78497 3.74851 3.69213C4.68256 2.5993 5.94485 1.83767 7.34712 1.52085C8.74939 1.20402 10.2165 1.34897 11.5297 1.93408"
                            stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        <path d="M15.4831 2.69385L8.81641 9.36718L6.81641 7.36718" stroke="#6B7280" stroke-width="1.33333"
                            stroke-linecap="round" stroke-linejoin="round" />
                    </g>
                    <defs>
                        <clipPath id="clip0_422_57362">
                            <rect width="16" height="16" fill="white" transform="translate(0.816406 0.0273438)" />
                        </clipPath>
                    </defs>
                </svg>

                <div @click="show_modal = !show_modal" class="txt_select_item ml-11 cur-pointer">Сохранить</div>
            </div>

            <!-- cancel bnt -->
            <div class="grey-box cntr-row a-c btn_cancel p-r cur-pointer h-40">
                <svg width="17" height="16" viewBox="0 0 17 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M8.01701 15.1668C4.06368 15.1668 0.850342 11.9535 0.850342 8.00016C0.850342 4.04683 4.06368 0.833496 8.01701 0.833496C11.9703 0.833496 15.1837 4.04683 15.1837 8.00016C15.1837 11.9535 11.9703 15.1668 8.01701 15.1668ZM8.01701 1.8335C4.61701 1.8335 1.85034 4.60016 1.85034 8.00016C1.85034 11.4002 4.61701 14.1668 8.01701 14.1668C11.417 14.1668 14.1837 11.4002 14.1837 8.00016C14.1837 4.60016 11.417 1.8335 8.01701 1.8335Z"
                        fill="#6B7280" />
                    <path
                        d="M6.13041 10.3869C6.00375 10.3869 5.87708 10.3402 5.77708 10.2402C5.58375 10.0469 5.58375 9.7269 5.77708 9.53357L9.55041 5.76023C9.74375 5.5669 10.0637 5.5669 10.2571 5.76023C10.4504 5.95357 10.4504 6.27357 10.2571 6.4669L6.48375 10.2402C6.39041 10.3402 6.25708 10.3869 6.13041 10.3869Z"
                        fill="#6B7280" />
                    <path
                        d="M9.90375 10.3869C9.77708 10.3869 9.65041 10.3402 9.55041 10.2402L5.77708 6.4669C5.58375 6.27357 5.58375 5.95357 5.77708 5.76023C5.97041 5.5669 6.29041 5.5669 6.48375 5.76023L10.2571 9.53357C10.4504 9.7269 10.4504 10.0469 10.2571 10.2402C10.1571 10.3402 10.0304 10.3869 9.90375 10.3869Z"
                        fill="#6B7280" />
                </svg>

                <div @click="show_modal = !show_modal" class="txt_select_item ml-11 cur-pointer">Отмена</div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    data() {
        return {
            input_bg_active: false,
            input_segment_connect_bg_active: false,
            input_dis_geo_active_bg: false,
            input_age_active_bg: false,
            input_interest_active_bg: false,
            show_select_item: false,
            show_select_item_dis_geo: false,
            show_config_age: false,
            show_select_item_interest: false,
            input_gender_active_bg: false,
            show_select_item_gender: false,
            show_segment_connect_select_item: false,
            selected_gender: '',
            is_check_connect: false,
            is_wrong_data: true
        }
    },
    components: {
    }
}

</script>


<style scoped>
.wrong_data {
    border: 1px solid #F87171 !important;
}
.mb-8 {
    margin-bottom: 8px;
}

.selected_color {
    color: #3B82F6 !important
}

.j-e {
    justify-content: end;
}

.ml-11 {
    margin-left: 11px;
}

.cur-pointer {
    cursor: pointer;
}

.h-40 {
    height: 40px;
}

.btn_cancel {
    padding: 0 16px;
}

.btn_cancel:hover {
    background-color: #F3F4F6;
}

.btn_save {
    padding: 0 16px;
    margin-right: 8px;
}

.btn_save:hover {
    background-color: #F3F4F6;
}

.grey-box {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
}

.cntr_select_item {
    display: flex;
    justify-content: left;
    width: 100%;
}

.cntr_select_item:first-child {
    margin-top: 8px;
}

.cntr_select_item:nth-child(n+2) {
    margin-top: 16px;
}

.txt_range_age {
    color: var(--d-9-d-9-d-9, #6B7280);
    font-family: Inter;
    font-size: 13.167px;
    font-style: normal;
    font-weight: 500;
    line-height: 14.483px;
    /* 110% */
    letter-spacing: 0.066px;
}

.cntr_input_range_label_min {
    position: absolute;
    top: 18px;
    left: 24px;
}

.input_range_label {
    position: absolute;
    top: 3px;
    left: 6px;
}

.cntr_input_range_label_max {
    position: absolute;
    top: 18px;
    right: 24px;
}

.cntr_input_range {
    margin-top: 53px;
    position: relative;
}

.input__range_min {
    position: absolute;
    top: 0;
    left: 21px;
    width: calc(50% - 21px);
}

.input__range_max {

    width: calc(50% - 21px);
    position: absolute;
    top: 0;
    right: 21px;
}

.rotate_180 {
    transform: rotate(180deg) translateY(50%) !important;
}

.cntr_config_age {
    position: absolute;
    bottom: -86px;
    width: 100%;
    height: 79px;
    flex-shrink: 0;
    border-radius: 7.9px;
    border: 1.317px solid #E5E7EB;
    background: #F3F4F6;
    box-shadow: 0px 10px 8px 0px rgba(0, 0, 0, 0.04), 0px 4px 3px 0px rgba(0, 0, 0, 0.10);
    box-sizing: border-box;
}

.txt_select_item {
    color: #6B7280;

    /* XS/Medium */
    font-family: Inter;
    font-size: 12px;
    font-style: normal;
    font-weight: 500;
    line-height: 16px;
    /* 133.333% */
    letter-spacing: 0.06px;
}

.p-r {
    position: relative;
}

input {
    outline: none;
}

.ml-12 {
    margin-left: 12px;
}

.mt-17 {
    margin-top: 17px;
}

.mt-13 {
    margin-top: 13px;
}

.mt-7 {
    margin-top: 7px;
}

.a-c {
    align-items: center;
}

.cntr-row {
    display: flex;
    position: relative;
}

.cntr_modal_new_segment {
    overflow: scroll;
    position: absolute;
    top: 60px;
    left: 0;
    width: 904px;
    height: 435px;
    flex-shrink: 0;

    border-radius: 8px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
    z-index: 20;

    padding: 45px 75px 0 45px;
    box-sizing: border-box;
}

.selected_item {
    position: absolute;
    bottom: -50px;

    display: flex;
    align-items: center;
    width: 100%;
    height: 48px;
    padding: 8px;

    border-radius: 8px;
    border: 1px solid #E5E7EB;
    background: #F3F4F6;

    /* Drop Shadow/lg */
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
    box-sizing: border-box;
    z-index: 15;
}

.selected_gender_item {
    position: relative;
    /* bottom: -119px; */
    width: 100%;
    height: 112px;
    padding: 8px;
    box-sizing: border-box;
    margin-top: 7px;
}

.box_select {
    border-radius: 8px;
    border: 1px solid var(--gray-200, #E5E7EB);
    background: #F3F4F6;
    box-shadow: 0px 4px 3px 0px rgba(0, 0, 0, 0.10), 0px 10px 8px 0px rgba(0, 0, 0, 0.04);
}

.input_segment {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;

    padding-left: 20px;
}

.input_segment:hover {
    background: #F3F4F6;
}

.input_segment_pars {
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;

    width: 100%;
    height: 44px;
    box-sizing: border-box;

    padding-left: 20px;
}

.input_segment_pars:hover {
    background: #F3F4F6;
}

.input__svg_arrow {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
}

.input_active_bg {
    background: #F3F4F6;
}

.txt_label {
    color: #000;
    font-family: Inter;
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: normal;
    letter-spacing: 0.08px;
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

.input_label {
    display: block;
    text-align: left;
    width: 100%;
    height: 37px;
}

.check_connect {
    position: relative;
    border-radius: 6px;
    border: 1px solid #E5E7EB;
    background: #FFF;
    width: 25px;
    height: 25px;
    cursor: pointer;
}

.check_connect_tick {
    position: relative;
    top: 4px;
    left: 2px;
}

/* INPUT RANGE */

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
</style>