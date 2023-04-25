<template>
    <div class="cntr-row">
        <part-left />

        <div class="cntr-bg-2">
            <div class="cntr-table">
                <div class="text-1">Добавить источник</div>

                <div class="line mt-10">
                </div>

                <!-- MENU -->
                <div class="cntr-row mt-18">

                    <!-- STATUS -->
                    <!-- <div class="grey-box w-78 h-40 cntr-row a-c pos-rel">
                        <svg class="ml-16" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path d="M15.3335 2.66669V6.66669H11.3335" stroke="#2564EB" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round"/>
                            <path d="M0.666504 13.3333V9.33331H4.6665" stroke="#2564EB" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round"/>
                            <path d="M2.33984 6.00001C2.67795 5.04453 3.25259 4.19028 4.01015 3.51696C4.7677 2.84363 5.68348 2.37319 6.67203 2.14952C7.66058 1.92584 8.68967 1.95624 9.6633 2.23786C10.6369 2.51948 11.5233 3.04315 12.2398 3.76001L15.3332 6.66668M0.666504 9.33334L3.75984 12.24C4.47634 12.9569 5.36275 13.4805 6.33638 13.7622C7.31 14.0438 8.3391 14.0742 9.32765 13.8505C10.3162 13.6268 11.232 13.1564 11.9895 12.4831C12.7471 11.8097 13.3217 10.9555 13.6598 10" stroke="#2564EB" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round"/>
                        </svg>

                        <svg class="ml-18" width="12" height="8" viewBox="0 0 12 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M5.69031 1.06524C5.73095 1.0245 5.77923 0.99217 5.83238 0.970115C5.88554 0.948059 5.94252 0.936707 6.00006 0.936707C6.05761 0.936707 6.11459 0.948059 6.16774 0.970115C6.22089 0.99217 6.26917 1.0245 6.30981 1.06524L11.5598 6.31524C11.642 6.39739 11.6881 6.50881 11.6881 6.62499C11.6881 6.74117 11.642 6.85259 11.5598 6.93474C11.4777 7.01689 11.3662 7.06304 11.2501 7.06304C11.1339 7.06304 11.0225 7.01689 10.9403 6.93474L6.00006 1.99361L1.05981 6.93474C0.977664 7.01689 0.866243 7.06304 0.750064 7.06304C0.633886 7.06304 0.522465 7.01689 0.440314 6.93474C0.358164 6.85259 0.312012 6.74117 0.312012 6.62499C0.312012 6.50881 0.358164 6.39739 0.440314 6.31524L5.69031 1.06524Z" fill="#374151"/>
                        </svg>

                        <selecter-status/>
                    </div> -->

                    <!-- NET -->
                    <div v-if="!is_selected"  class="grey-box w-113 h-40 cntr-row a-c pos-rel cur-pointer"
                        v-on:mouseover="show_selecter=true"
                        v-on:mouseleave="show_selecter=false"
                    >
                        
                        <svg class="ml-16" width="16" height="14" viewBox="0 0 16 14" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                        </svg>

                        <div class="text-2 ml-11">Сеть</div>

                        <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                        <selecter-net v-if="show_selecter" 
                            v-on:mouseover="show_selecter=true"
                            v-on:mouseleave="show_selecter=false"
                        />
                    </div>
                    <div v-if="is_selected"  class="grey-box w-137 h-40 cntr-row a-c pos-rel cur-pointer"
                        v-on:mouseover="show_selecter=true"
                        v-on:mouseleave="show_selecter=false"
                    >
                        
                        <svg class="ml-16"  width="19" height="19" viewBox="0 0 19 19" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path 
                                stroke="#3B82F6" 
                                
                                fill-rule="evenodd" clip-rule="evenodd" d="M12.6287 1.20898L11.7167 2.12549C11.5302 2.31289 11.4255 2.5665 11.4255 2.83087V4.13791V5.44126C11.4255 5.70781 11.3191 5.96333 11.1299 6.15108L10.4939 6.7822C9.59663 7.67256 9.53696 7.7068 8.87815 7.70969C7.91972 7.71396 7.12533 8.11108 6.65615 8.82076C6.13128 9.61474 6.10722 10.8597 6.60266 11.5828C7.05726 12.2462 7.73587 12.6779 8.45133 12.7585C10.0163 12.9349 11.288 11.7962 11.288 10.2183C11.288 9.57885 11.3224 9.52205 12.2882 8.56266L12.9958 7.85971C13.1832 7.67361 13.4365 7.56916 13.7006 7.56916H14.938H16.1723C16.4383 7.56916 16.6934 7.46316 16.881 7.27461L17.8196 6.33158V6.33158C18.2751 5.87395 17.951 5.094 17.3053 5.094H16.4791H14.8921C14.3456 5.094 13.9003 4.65519 13.8922 4.10869L13.8693 2.54707L13.8569 1.70549C13.8476 1.0694 13.0774 0.758072 12.6287 1.20898V1.20898ZM6.88772 2.69902C4.77655 3.25593 2.69027 4.93353 1.81379 6.77903C0.319757 9.92509 0.909393 13.3372 3.36447 15.7513C5.36426 17.7176 7.9816 18.4322 10.6677 17.7452C12.7923 17.2018 14.6139 15.7923 15.5847 13.9403C16.121 12.9174 16.5133 11.5972 16.5133 10.8152V10.8152C16.5133 10.5413 16.2913 10.3193 16.0175 10.3193H15.2887H14.7472C14.3557 10.3193 14.0243 10.6083 13.9709 10.9961V10.9961C13.5853 13.7995 10.7095 15.9081 7.93746 15.4198C4.45271 14.8061 2.52319 11.0598 4.06673 7.90495C4.74904 6.51034 6.48922 5.241 8.02216 5.01961V5.01961C8.39709 4.96547 8.67533 4.64415 8.67533 4.26534V3.70324V2.99708C8.67533 2.71373 8.44298 2.48543 8.15967 2.49042V2.49042C7.87613 2.49537 7.30368 2.58929 6.88772 2.69902Z"  stroke-width="1.3"
                            />
                        </svg>
                        <div class="text-2-selected ml-11">MyTarget</div>

                        <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                        <selecter-net v-if="show_selecter" 
                            v-on:mouseover="show_selecter=true"
                            v-on:mouseleave="show_selecter=false"
                        />
                    </div>

                    <!-- ACCOUNT -->
                    <div v-if="!is_selected_account" class="grey-box w-113 h-40 cntr-row a-c ml-8">
                        <svg class="ml-16" width="16" height="16" viewBox="0 0 16 16" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M7.33333 12.6667C10.2789 12.6667 12.6667 10.2789 12.6667 7.33333C12.6667 4.38781 10.2789 2 7.33333 2C4.38781 2 2 4.38781 2 7.33333C2 10.2789 4.38781 12.6667 7.33333 12.6667Z"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                            <path d="M14.0001 14L11.1001 11.1" stroke="#6B7280" stroke-width="1.33333"
                                stroke-linecap="round" stroke-linejoin="round" />
                        </svg>
                        <div class="text-2 ml-11">Аккаунт</div>
                    </div>
                    <div v-if="is_selected_account" class="light-blue-box w-150 h-40 cntr-row a-c ml-8">
                        <svg class="ml-16" width="16" height="16" viewBox="0 0 16 16" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M7.33333 12.6667C10.2789 12.6667 12.6667 10.2789 12.6667 7.33333C12.6667 4.38781 10.2789 2 7.33333 2C4.38781 2 2 4.38781 2 7.33333C2 10.2789 4.38781 12.6667 7.33333 12.6667Z"
                                stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                            <path d="M14.0001 14L11.1001 11.1" stroke="#6B7280" stroke-width="1.33333"
                                stroke-linecap="round" stroke-linejoin="round" />
                        </svg>
                        <div class="text-2 ml-11">mail@gmail.com</div>
                    </div>



                    <!-- DATE CREATE -->
                    <div class="grey-box cntr-row a-c w-233 ml-8">
                        <svg class="ml-16" width="11" height="12" viewBox="0 0 11 12" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <g clip-path="url(#clip0_35_59414)">
                                <path d="M7.66683 5.00002L8.3335 5.00002L8.3335 5.66669H7.66683V5.00002Z" fill="#1F2937"
                                    stroke="#6B7280" stroke-width="0.666667" />
                                <path
                                    d="M2.33333 0.666687C2.42174 0.666687 2.50652 0.701806 2.56904 0.764318C2.63155 0.82683 2.66667 0.911615 2.66667 1.00002V1.33335H8V1.00002C8 0.911615 8.03512 0.82683 8.09763 0.764318C8.16014 0.701806 8.24493 0.666687 8.33333 0.666687C8.42174 0.666687 8.50652 0.701806 8.56904 0.764318C8.63155 0.82683 8.66667 0.911615 8.66667 1.00002V1.33335H9.33333C9.68696 1.33335 10.0261 1.47383 10.2761 1.72388C10.5262 1.97393 10.6667 2.31307 10.6667 2.66669V10C10.6667 10.3536 10.5262 10.6928 10.2761 10.9428C10.0261 11.1929 9.68696 11.3334 9.33333 11.3334H1.33333C0.979711 11.3334 0.640573 11.1929 0.390524 10.9428C0.140476 10.6928 0 10.3536 0 10V2.66669C0 2.31307 0.140476 1.97393 0.390524 1.72388C0.640573 1.47383 0.979711 1.33335 1.33333 1.33335H2V1.00002C2 0.911615 2.03512 0.82683 2.09763 0.764318C2.16014 0.701806 2.24493 0.666687 2.33333 0.666687V0.666687ZM0.666667 3.33335V10C0.666667 10.1768 0.736905 10.3464 0.861929 10.4714C0.986953 10.5964 1.15652 10.6667 1.33333 10.6667H9.33333C9.51014 10.6667 9.67971 10.5964 9.80474 10.4714C9.92976 10.3464 10 10.1768 10 10V3.33335H0.666667Z"
                                    fill="#1F2937" />
                            </g>
                            <defs>
                                <clipPath id="clip0_35_59414">
                                    <rect width="10.6667" height="10.6667" fill="white" transform="translate(0 0.666687)" />
                                </clipPath>
                            </defs>
                        </svg>

                        <div class="text-2 ml-11 ml-8">Выберите дату создания</div>

                        <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>
                    </div>

                    <!-- DATE UPDATE -->
                    <div class="grey-box cntr-row a-c w-233 ml-8">
                        <svg class="ml-16" width="11" height="12" viewBox="0 0 11 12" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <g clip-path="url(#clip0_35_59414)">
                                <path d="M7.66683 5.00002L8.3335 5.00002L8.3335 5.66669H7.66683V5.00002Z" fill="#1F2937"
                                    stroke="#6B7280" stroke-width="0.666667" />
                                <path
                                    d="M2.33333 0.666687C2.42174 0.666687 2.50652 0.701806 2.56904 0.764318C2.63155 0.82683 2.66667 0.911615 2.66667 1.00002V1.33335H8V1.00002C8 0.911615 8.03512 0.82683 8.09763 0.764318C8.16014 0.701806 8.24493 0.666687 8.33333 0.666687C8.42174 0.666687 8.50652 0.701806 8.56904 0.764318C8.63155 0.82683 8.66667 0.911615 8.66667 1.00002V1.33335H9.33333C9.68696 1.33335 10.0261 1.47383 10.2761 1.72388C10.5262 1.97393 10.6667 2.31307 10.6667 2.66669V10C10.6667 10.3536 10.5262 10.6928 10.2761 10.9428C10.0261 11.1929 9.68696 11.3334 9.33333 11.3334H1.33333C0.979711 11.3334 0.640573 11.1929 0.390524 10.9428C0.140476 10.6928 0 10.3536 0 10V2.66669C0 2.31307 0.140476 1.97393 0.390524 1.72388C0.640573 1.47383 0.979711 1.33335 1.33333 1.33335H2V1.00002C2 0.911615 2.03512 0.82683 2.09763 0.764318C2.16014 0.701806 2.24493 0.666687 2.33333 0.666687V0.666687ZM0.666667 3.33335V10C0.666667 10.1768 0.736905 10.3464 0.861929 10.4714C0.986953 10.5964 1.15652 10.6667 1.33333 10.6667H9.33333C9.51014 10.6667 9.67971 10.5964 9.80474 10.4714C9.92976 10.3464 10 10.1768 10 10V3.33335H0.666667Z"
                                    fill="#1F2937" />
                            </g>
                            <defs>
                                <clipPath id="clip0_35_59414">
                                    <rect width="10.6667" height="10.6667" fill="white" transform="translate(0 0.666687)" />
                                </clipPath>
                            </defs>
                        </svg>

                        <div class="text-2 ml-11 ml-8">Выберите дату обновления</div>

                        <svg class="ml-14" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>
                    </div>

                    <!-- STATUS -->
                    <div class="grey-box cntr-row a-c j-b w-148 ml-8 pos-rel" 
                        v-if="!is_selected_status"
                        v-on:mouseover="show_selecter_status=true"
                        v-on:mouseleave="show_selecter_status=false"
                    >
                        <div class="cntr-row">
                            <svg class="ml-16" width="16" height="14" viewBox="0 0 16 14" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                    stroke="#6B7280" stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                            </svg>

                            <div class="text-2 ml-11">Статус</div>
                        </div>
                        

                        <svg class="mr-16" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                        <selecter-connect v-if="show_selecter_status"
                            v-on:mouseover="show_selecter_status=true"
                            v-on:mouseleave="show_selecter_status=false"
                        />
                    </div>
                    <div class="grey-box cntr-row a-c j-b w-155 ml-8 pos-rel" 
                        v-if="is_selected_status"
                        v-on:mouseover="show_selecter_status=true"
                        v-on:mouseleave="show_selecter_status=false"
                    >
                        <div class="cntr-row">
                            <svg class="ml-16" width="16" height="14" viewBox="0 0 16 14" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path d="M14.6668 1H1.3335L6.66683 7.30667V11.6667L9.3335 13V7.30667L14.6668 1Z"
                                    stroke="#3B82F6"  stroke-width="1.33333" stroke-linecap="round" stroke-linejoin="round" />
                            </svg>

                            <div class="text-2-selected ml-11">Подключено</div>
                        </div>
                        

                        <svg class="mr-16" width="12" height="8" viewBox="0 0 12 8" fill="none"
                            xmlns="http://www.w3.org/2000/svg">
                            <path fill-rule="evenodd" clip-rule="evenodd"
                                d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                fill="#374151" />
                        </svg>

                        <selecter-connect v-if="show_selecter_status"
                            v-on:mouseover="show_selecter_status=true"
                            v-on:mouseleave="show_selecter_status=false"
                        />
                    </div>

                    <!-- BUTTON -->
                    <div class="btn-blue-box a-c cntr-row j-c text-white mt-15 ml-8 cur-pointer">Добавить аккаунт</div>
                </div>

                <!-- HEADERS -->
                <div class="cntr-row h-40 a-c mt-18">
                    <div class="text-2 w-56">ID</div>

                    <div v-if="!is_sorted" class="text-2 w-213">Сеть</div>
                    <div v-if="is_sorted" class="text-2-selected w-213">Сеть
                        <span class="ml-14">
                            <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd" d="M3.99986 8.26636e-05C3.86725 8.2652e-05 3.74007 0.0527607 3.6463 0.146529C3.55254 0.240297 3.49986 0.367474 3.49986 0.500083L3.49986 6.29308L1.35386 4.14608C1.30737 4.09959 1.25218 4.06272 1.19144 4.03756C1.1307 4.0124 1.0656 3.99945 0.999857 3.99945C0.934113 3.99945 0.869013 4.0124 0.808273 4.03756C0.747534 4.06272 0.692345 4.09959 0.645857 4.14608C0.599369 4.19257 0.562492 4.24776 0.537333 4.3085C0.512174 4.36924 0.499225 4.43434 0.499225 4.50008C0.499225 4.56583 0.512174 4.63093 0.537333 4.69167C0.562492 4.75241 0.599369 4.80759 0.645857 4.85408L3.64586 7.85408C3.6923 7.90065 3.74748 7.93759 3.80822 7.9628C3.86897 7.988 3.93409 8.00098 3.99986 8.00098C4.06562 8.00098 4.13074 7.988 4.19149 7.9628C4.25224 7.93759 4.30741 7.90065 4.35386 7.85408L7.35386 4.85408C7.44774 4.7602 7.50049 4.63286 7.50049 4.50008C7.50049 4.36731 7.44774 4.23997 7.35386 4.14608C7.25997 4.0522 7.13263 3.99945 6.99986 3.99945C6.86708 3.99945 6.73974 4.0522 6.64586 4.14608L4.49986 6.29308L4.49986 0.500083C4.49986 0.367474 4.44718 0.240297 4.35341 0.146529C4.25964 0.0527608 4.13247 8.26752e-05 3.99986 8.26636e-05Z" fill="#006AFF"/>
                            </svg>
                        </span>
                    </div>

                    <div class="text-2 w-188">Логин</div>
                    <div class="text-2 w-179">Дата создания</div>
                    <div class="text-2 w-179">Дата обновления</div>

                    <div v-if="!is_sorted_status" class="text-2 w-150">
                        Статус
                    </div>
                    <div v-if="is_sorted_status" class="text-2-selected w-150">
                        Статус
                        <span class="ml-14">
                            <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd" d="M4.00014 7.99992C4.13275 7.99992 4.25993 7.94724 4.3537 7.85347C4.44747 7.7597 4.50014 7.63253 4.50014 7.49992L4.50014 1.70692L6.64614 3.85392C6.69263 3.90041 6.74782 3.93728 6.80856 3.96244C6.8693 3.9876 6.9344 4.00055 7.00014 4.00055C7.06589 4.00055 7.13099 3.9876 7.19173 3.96244C7.25247 3.93728 7.30766 3.90041 7.35414 3.85392C7.40063 3.80743 7.43751 3.75224 7.46267 3.6915C7.48783 3.63076 7.50077 3.56566 7.50077 3.49992C7.50077 3.43417 7.48783 3.36907 7.46267 3.30833C7.43751 3.24759 7.40063 3.19241 7.35414 3.14592L4.35414 0.145917C4.3077 0.0993539 4.25252 0.062411 4.19178 0.0372045C4.13103 0.0119981 4.06591 -0.000976563 4.00014 -0.000976563C3.93438 -0.000976563 3.86926 0.0119981 3.80851 0.0372045C3.74776 0.062411 3.69259 0.0993539 3.64614 0.145917L0.646143 3.14592C0.552257 3.2398 0.499512 3.36714 0.499512 3.49992C0.499512 3.63269 0.552257 3.76003 0.646143 3.85392C0.74003 3.9478 0.867368 4.00055 1.00014 4.00055C1.13292 4.00055 1.26026 3.9478 1.35414 3.85392L3.50014 1.70692L3.50014 7.49992C3.50014 7.63253 3.55282 7.7597 3.64659 7.85347C3.74036 7.94724 3.86754 7.99992 4.00014 7.99992Z" fill="#006AFF"/>
                            </svg>
                        </span>
                    </div>

                    <div class="text-2 w-87">
                        ACTION
                    </div>
                </div>

                <div class="line">
                </div>

                <div v-for="account in accounts" v-bind:key="account.id">
                    <div class="cntr-row h-40 a-c">
                        <div class="text-3 w-56">{{ account.id }}</div>
                        <div class="text-4 w-213">{{ account.src }}</div>
                        <div class="text-3 w-188">{{ account.email }}</div>
                        <div class="text-5 w-179">{{ account.date }}</div>
                        <div class="text-5 w-179">{{ account.date }}</div>
                        <div class="text-5 w-150">{{ account.status }}</div>
                        <div class="text-5 w-87">
                            <div class="cntr-row">
                                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M16 8C16 12.4183 12.4183 16 8 16C3.58172 16 0 12.4183 0 8C0 3.58172 3.58172 0 8 0C12.4183 0 16 3.58172 16 8Z" fill="#84CC16"/>
                                    <path d="M11.8998 4.98919C11.964 5.05355 12 5.14073 12 5.23161C12 5.32249 11.964 5.40967 11.8998 5.47403L11.1834 6.191L9.80975 4.8175L10.5261 4.10054C10.5905 4.03616 10.6779 4 10.7689 4C10.86 4 10.9473 4.03616 11.0117 4.10054L11.8998 4.98919ZM10.6978 6.67584L9.32416 5.30234L4.64474 9.98184C4.60694 10.0196 4.57848 10.0657 4.56164 10.1164L4.00873 11.7743C3.99871 11.8045 3.99728 11.8369 4.00462 11.8679C4.01196 11.8989 4.02777 11.9272 4.05029 11.9497C4.07281 11.9722 4.10115 11.988 4.13214 11.9954C4.16313 12.0027 4.19555 12.0013 4.22577 11.9913L5.8838 11.4384C5.93446 11.4218 5.98055 11.3936 6.01842 11.356L10.6978 6.67584Z" fill="white"/>
                                </svg>
                                <svg class="ml-10" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                                    <path d="M16 8C16 10.1217 15.1571 12.1566 13.6569 13.6569C12.1566 15.1571 10.1217 16 8 16C5.87827 16 3.84344 15.1571 2.34315 13.6569C0.842855 12.1566 0 10.1217 0 8C0 5.87827 0.842855 3.84344 2.34315 2.34315C3.84344 0.842855 5.87827 0 8 0C10.1217 0 12.1566 0.842855 13.6569 2.34315C15.1571 3.84344 16 5.87827 16 8ZM5.354 4.646C5.26011 4.55211 5.13278 4.49937 5 4.49937C4.86722 4.49937 4.73989 4.55211 4.646 4.646C4.55211 4.73989 4.49937 4.86722 4.49937 5C4.49937 5.13278 4.55211 5.26011 4.646 5.354L7.293 8L4.646 10.646C4.59951 10.6925 4.56264 10.7477 4.53748 10.8084C4.51232 10.8692 4.49937 10.9343 4.49937 11C4.49937 11.0657 4.51232 11.1308 4.53748 11.1916C4.56264 11.2523 4.59951 11.3075 4.646 11.354C4.73989 11.4479 4.86722 11.5006 5 11.5006C5.06574 11.5006 5.13084 11.4877 5.19158 11.4625C5.25232 11.4374 5.30751 11.4005 5.354 11.354L8 8.707L10.646 11.354C10.6925 11.4005 10.7477 11.4374 10.8084 11.4625C10.8692 11.4877 10.9343 11.5006 11 11.5006C11.0657 11.5006 11.1308 11.4877 11.1916 11.4625C11.2523 11.4374 11.3075 11.4005 11.354 11.354C11.4005 11.3075 11.4374 11.2523 11.4625 11.1916C11.4877 11.1308 11.5006 11.0657 11.5006 11C11.5006 10.9343 11.4877 10.8692 11.4625 10.8084C11.4374 10.7477 11.4005 10.6925 11.354 10.646L8.707 8L11.354 5.354C11.4005 5.30751 11.4374 5.25232 11.4625 5.19158C11.4877 5.13084 11.5006 5.06574 11.5006 5C11.5006 4.93426 11.4877 4.86916 11.4625 4.80842C11.4374 4.74768 11.4005 4.69249 11.354 4.646C11.3075 4.59951 11.2523 4.56264 11.1916 4.53748C11.1308 4.51232 11.0657 4.49937 11 4.49937C10.9343 4.49937 10.8692 4.51232 10.8084 4.53748C10.7477 4.56264 10.6925 4.59951 10.646 4.646L8 7.293L5.354 4.646Z" fill="#EF4444"/>
                                </svg>
                            </div>
                        </div>
                        <!-- <div class="w-113 txt-a-l">
                            <svg-accept />
                        </div> -->
                    </div>
                    <div class="line">
                    </div>
                </div>

                <div class="cntr-row j-b a-c mt-20">
                    <div class="cntr-row">
                        <div class="grey-box w-97 h-40 cntr-row a-c">
                            <svg class="ml-16" width="8" height="14" viewBox="0 0 8 14" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M7.35404 0.646009C7.4006 0.692455 7.43754 0.74763 7.46275 0.808375C7.48796 0.86912 7.50093 0.934242 7.50093 1.00001C7.50093 1.06578 7.48796 1.1309 7.46275 1.19164C7.43754 1.25239 7.4006 1.30756 7.35404 1.35401L1.70704 7.00001L7.35404 12.646C7.44793 12.7399 7.50067 12.8672 7.50067 13C7.50067 13.1328 7.44793 13.2601 7.35404 13.354C7.26015 13.4479 7.13281 13.5006 7.00004 13.5006C6.86726 13.5006 6.73993 13.4479 6.64604 13.354L0.646039 7.35401C0.599476 7.30756 0.562533 7.25239 0.537326 7.19164C0.51212 7.1309 0.499146 7.06578 0.499146 7.00001C0.499146 6.93424 0.51212 6.86912 0.537326 6.80838C0.562533 6.74763 0.599476 6.69245 0.646039 6.64601L6.64604 0.646009C6.69248 0.599446 6.74766 0.562503 6.80841 0.537296C6.86915 0.51209 6.93427 0.499115 7.00004 0.499115C7.06581 0.499115 7.13093 0.51209 7.19167 0.537296C7.25242 0.562503 7.30759 0.599446 7.35404 0.646009Z"
                                    fill="#6B7280" />
                            </svg>
                            <div class="text-2 ml-11">Назад</div>
                        </div>

                        <div class="num-page-box num-page-txt a-c cntr-row j-c">1</div>

                        <div class="blue-box a-c cntr-row j-c text-white ml-10">2</div>

                        <div class="num-page-box num-page-txt a-c cntr-row j-c">3</div>

                        <div class="num-page-box num-page-txt a-c cntr-row j-c">...</div>

                        <div class="num-page-box num-page-txt a-c cntr-row j-c">10</div>

                        <div class="grey-box w-98 h-40 cntr-row a-c ml-10">

                            <div class="text-2 ml-16">Далее</div>

                            <svg class="ml-11" width="8" height="14" viewBox="0 0 8 14" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M0.646039 0.646009C0.692485 0.599446 0.74766 0.562503 0.808405 0.537296C0.869151 0.51209 0.934272 0.499115 1.00004 0.499115C1.06581 0.499115 1.13093 0.51209 1.19167 0.537296C1.25242 0.562503 1.30759 0.599446 1.35404 0.646009L7.35404 6.64601C7.4006 6.69245 7.43754 6.74763 7.46275 6.80838C7.48796 6.86912 7.50093 6.93424 7.50093 7.00001C7.50093 7.06578 7.48796 7.1309 7.46275 7.19164C7.43754 7.25239 7.4006 7.30756 7.35404 7.35401L1.35404 13.354C1.26015 13.4479 1.13281 13.5006 1.00004 13.5006C0.867263 13.5006 0.739926 13.4479 0.646039 13.354C0.552152 13.2601 0.499407 13.1328 0.499407 13C0.499407 12.8672 0.552152 12.7399 0.646039 12.646L6.29304 7.00001L0.646039 1.35401C0.599476 1.30756 0.562533 1.25239 0.537326 1.19164C0.51212 1.1309 0.499146 1.06578 0.499146 1.00001C0.499146 0.934242 0.51212 0.86912 0.537326 0.808375C0.562533 0.74763 0.599476 0.692455 0.646039 0.646009Z"
                                    fill="#6B7280" />
                            </svg>
                        </div>
                    </div>

                    <div class="cntr-row a-c">
                        <div class="text-2">Показать</div>
                        <div class="grey-box w-113 h-40 cntr-row a-c j-b ml-11">

                            <div class="text-2 ml-11">10</div>

                            <svg class="mr-16" width="12" height="8" viewBox="0 0 12 8" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M6.30969 6.93476C6.26905 6.9755 6.22077 7.00783 6.16762 7.02988C6.11446 7.05194 6.05748 7.06329 5.99994 7.06329C5.94239 7.06329 5.88541 7.05194 5.83226 7.02988C5.77911 7.00783 5.73083 6.9755 5.69019 6.93476L0.440187 1.68476C0.358037 1.60261 0.311884 1.49119 0.311884 1.37501C0.311884 1.25883 0.358037 1.14741 0.440187 1.06526C0.522337 0.98311 0.633758 0.936958 0.749938 0.936958C0.866116 0.936958 0.977537 0.98311 1.05969 1.06526L5.99994 6.00639L10.9402 1.06526C11.0223 0.983111 11.1338 0.936959 11.2499 0.936959C11.3661 0.936959 11.4775 0.983111 11.5597 1.06526C11.6418 1.14741 11.688 1.25883 11.688 1.37501C11.688 1.49119 11.6418 1.60261 11.5597 1.68476L6.30969 6.93476Z"
                                    fill="#374151" />
                            </svg>

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
import SelecterNet from './SelecterNet.vue'
import SelecterConnect from './SelecterConnect.vue'

import PartLeft from './PartLeft.vue'

export default {
    name: 'AddSource',
    data() {
        return {
            accounts: [
                { id: 1, src: 'MyTarget', email: 'dsg@mail.ru', date: '12.03.2023', is_actual: 'Неактуален', status: 'Не подключено' },
                { id: 2, src: 'MyTarget', email: 'dsg@mail.ru', date: '12.03.2023', is_actual: 'Неактуален', status: 'Подключено' }
            ],
            is_sorted: true,
            is_sorted_status: true,
            is_selected: true,
            is_selected_account: true,
            is_selected_status: true,
            show_selecter: false,
            show_selecter_status: false,
        }
    },
    components: {
        // 'svg-accept': SvgAccept,
        // 'svg-cancel': SvgCancel,
        // 'svg-stop': SvgStop,
        // 'svg-attention': SvgAttention,
        'selecter-connect': SelecterConnect,
        // 'selecter-status': SelecterStatus,
        'part-left': PartLeft,
        'selecter-net': SelecterNet
    }
}



</script>

<style scoped>
.cur-pointer {
    cursor: pointer;
}
.pos-rel {
    position: relative;
}

.txt-a-l {
    text-align: left;
}

.line {
    /* width: 1050px; */
    height: 1px;

    background: #E5E7EB;
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

.text-2-selected {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 12px;
    line-height: 16px;
    /* identical to box height, or 133% */

    letter-spacing: 0.005em;
    text-align: left;
    /* Gray/500 */

    color: #3B82F6;
}



.text-3 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 14px;
    line-height: 20px;
    /* identical to box height, or 143% */
    text-align: left;
    letter-spacing: 0.005em;

    /* Gray/800 */

    color: #1F2937;
}

.text-4 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 20px;
    /* identical to box height, or 143% */

    text-align: left;
    letter-spacing: 0.005em;

    /* Blue/500 */

    color: #3B82F6;
}

.text-5 {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 600;
    font-size: 14px;
    line-height: 20px;
    /* identical to box height, or 143% */

    text-align: left;
    letter-spacing: 0.005em;

    /* Static */

    color: #6B7280;
}

.text-white {
    font-family: 'Inter';
    font-style: normal;
    font-weight: 500;
    font-size: 16px;
    line-height: 24px;
    /* identical to box height, or 150% */

    text-align: center;
    letter-spacing: 0.005em;

    /* White/White */

    color: #FFFFFF;
}

.cntr-table {
    padding-left: 26px;
    padding-top: 21px;
    padding-right: 27px;
}

.cntr-bg-2 {
    background: #FFFFFF;
    /* width: 70%; */
}

.cntr-row {
    display: flex;
}

.grey-box {
    border: 1px solid #E5E7EB;
    /* Drop Shadow/sm */

    box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
    border-radius: 6px;
}

    .light-blue-box {

        background: #F2F7FF;
        /* Gray/200 */

        border: 1px solid #E5E7EB;
        /* Drop Shadow/sm */

        box-shadow: 0px 1px 2px rgba(0, 0, 0, 0.05);
        border-radius: 6px;
    }

    .blue-box {
        width: 40px;
        height: 40px;

        /* Blue/500 */

        background: #3B82F6;
        border-radius: 6px;
    }

    .btn-blue-box {
        width: 161px;
        height: 38px;

        /* Blue/500 */

        background: #3B82F6;
        border-radius: 6px;
    }

    .num-page-box {
        width: 40px;
        height: 40px;

        background: #FFFFFF;
        border-radius: 6px;
    }

    .num-page-txt {
        font-family: 'Inter';
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 24px;
        /* identical to box height, or 150% */

        text-align: center;
        letter-spacing: 0.005em;

        color: #6B7280;
    }
</style>