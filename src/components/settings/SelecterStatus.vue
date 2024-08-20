<template>
    <div class="wrap__cntr-selecter">
        <div class="cntr-selecter">
            <div class="cntr-selecter-item box-select">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M7.38021 12.1136C7.26688 12.1136 7.16021 12.0936 7.04688 12.0536C6.68021 11.9136 6.44021 11.5736 6.44021 11.1802V8.98024H5.78688C5.41355 8.98024 5.08688 8.76691 4.93355 8.43357C4.78021 8.09357 4.84021 7.71357 5.08688 7.43357L7.92688 4.20691C8.18688 3.91357 8.58688 3.81357 8.95355 3.95357C9.32021 4.09357 9.56021 4.43357 9.56021 4.82691V7.02691H10.2202C10.5935 7.02691 10.9202 7.24024 11.0735 7.57357C11.2269 7.91357 11.1669 8.29357 10.9202 8.57357L8.08021 11.8002C7.89355 12.0002 7.64021 12.1136 7.38021 12.1136ZM5.93355 7.98024H6.94021C7.21355 7.98024 7.44021 8.20691 7.44021 8.48024V11.0002L10.0669 8.02024H9.06021C8.78688 8.02024 8.56021 7.79357 8.56021 7.52024V5.00024L5.93355 7.98024Z"
                        fill="#27AE60" />
                    <path
                        d="M7.98014 15.1668C4.03348 15.1668 0.813477 11.9535 0.813477 8.00016C0.813477 4.04683 4.03348 0.833496 7.98014 0.833496C11.9268 0.833496 15.1468 4.04683 15.1468 8.00016C15.1468 11.9535 11.9335 15.1668 7.98014 15.1668ZM7.98014 1.8335C4.58014 1.8335 1.81348 4.60016 1.81348 8.00016C1.81348 11.4002 4.58014 14.1668 7.98014 14.1668C11.3801 14.1668 14.1468 11.4002 14.1468 8.00016C14.1468 4.60016 11.3801 1.8335 7.98014 1.8335Z"
                        fill="#27AE60" />
                </svg>

                <div class="text-2 color-1 ml-8">Создана</div>
            </div>
            <div class="cntr-selecter-item box-select">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M5.76 14.5H3.34C2.1 14.5 1.5 13.9267 1.5 12.74V3.26C1.5 2.07333 2.1 1.5 3.34 1.5H5.76C7 1.5 7.6 2.07333 7.6 3.26V12.74C7.6 13.9267 7 14.5 5.76 14.5ZM3.34 2.5C2.62 2.5 2.5 2.68 2.5 3.26V12.74C2.5 13.32 2.61333 13.5 3.34 13.5H5.76C6.48 13.5 6.6 13.32 6.6 12.74V3.26C6.6 2.68 6.48667 2.5 5.76 2.5H3.34Z"
                        fill="#27AE60" />
                    <path
                        d="M12.6599 14.5H10.2399C8.9999 14.5 8.3999 13.9267 8.3999 12.74V3.26C8.3999 2.07333 8.9999 1.5 10.2399 1.5H12.6599C13.8999 1.5 14.4999 2.07333 14.4999 3.26V12.74C14.4999 13.9267 13.8999 14.5 12.6599 14.5ZM10.2399 2.5C9.5199 2.5 9.3999 2.68 9.3999 3.26V12.74C9.3999 13.32 9.51324 13.5 10.2399 13.5H12.6599C13.3799 13.5 13.4999 13.32 13.4999 12.74V3.26C13.4999 2.68 13.3866 2.5 12.6599 2.5H10.2399Z"
                        fill="#27AE60" />
                </svg>


                <div class="text-2 color-1 ml-8">Выполняется</div>
            </div>
            <div class="cntr-selecter-item box-select">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M8.00016 15.1668C4.04683 15.1668 0.833496 11.9535 0.833496 8.00016C0.833496 4.04683 4.04683 0.833496 8.00016 0.833496C11.9535 0.833496 15.1668 4.04683 15.1668 8.00016C15.1668 11.9535 11.9535 15.1668 8.00016 15.1668ZM8.00016 1.8335C4.60016 1.8335 1.8335 4.60016 1.8335 8.00016C1.8335 11.4002 4.60016 14.1668 8.00016 14.1668C11.4002 14.1668 14.1668 11.4002 14.1668 8.00016C14.1668 4.60016 11.4002 1.8335 8.00016 1.8335Z"
                        fill="#27AE60" />
                    <path
                        d="M7.05346 10.3867C6.92012 10.3867 6.79346 10.3334 6.70012 10.2401L4.81346 8.3534C4.62012 8.16007 4.62012 7.84007 4.81346 7.64673C5.00679 7.4534 5.32679 7.4534 5.52012 7.64673L7.05346 9.18007L10.4801 5.7534C10.6735 5.56007 10.9935 5.56007 11.1868 5.7534C11.3801 5.94673 11.3801 6.26673 11.1868 6.46006L7.40679 10.2401C7.31346 10.3334 7.18679 10.3867 7.05346 10.3867Z"
                        fill="#27AE60" />
                </svg>


                <div class="text-2 color-1 ml-8">Выполнена</div>
            </div>
            <div class="cntr-selecter-item box-select">
                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M6.86001 2.57347L1.21335 12.0001C1.09693 12.2018 1.03533 12.4303 1.03467 12.6631C1.03402 12.896 1.09434 13.1249 1.20963 13.3272C1.32492 13.5294 1.49116 13.698 1.69182 13.816C1.89247 13.9341 2.12055 13.9976 2.35335 14.0001H13.6467C13.8795 13.9976 14.1076 13.9341 14.3082 13.816C14.5089 13.698 14.6751 13.5294 14.7904 13.3272C14.9057 13.1249 14.966 12.896 14.9654 12.6631C14.9647 12.4303 14.9031 12.2018 14.7867 12.0001L9.14001 2.57347C9.02117 2.37754 8.85383 2.21555 8.65414 2.10313C8.45446 1.9907 8.22917 1.93164 8.00001 1.93164C7.77086 1.93164 7.54557 1.9907 7.34588 2.10313C7.1462 2.21555 6.97886 2.37754 6.86001 2.57347V2.57347Z"
                        stroke="#F87171" stroke-linecap="round" stroke-linejoin="round" />
                    <path d="M8 6V8.66667" stroke="#F87171" stroke-width="1.33333" stroke-linecap="round"
                        stroke-linejoin="round" />
                    <path d="M8 11.3335H8.0075" stroke="#F87171" stroke-width="1.33333" stroke-linecap="round"
                        stroke-linejoin="round" />
                </svg>


                <div class="text-2 color-1 ml-8">Остановлена</div>
            </div>
            <div class="cntr-selecter-item box-select">

                <svg width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M5.2465 14.1865C4.71984 14.1865 4.21984 14.0598 3.77984 13.8065C2.73984 13.2065 2.1665 11.9865 2.1665 10.3798V5.6265C2.1665 4.01316 2.73984 2.79983 3.77984 2.19983C4.81984 1.59983 6.15984 1.71316 7.55984 2.51983L11.6732 4.89316C13.0665 5.69983 13.8398 6.8065 13.8398 8.0065C13.8398 9.2065 13.0732 10.3132 11.6732 11.1198L7.55984 13.4932C6.75317 13.9532 5.9665 14.1865 5.2465 14.1865ZM5.2465 2.81316C4.8865 2.81316 4.5665 2.89316 4.27984 3.05983C3.55984 3.47316 3.1665 4.3865 3.1665 5.6265V10.3732C3.1665 11.6132 3.55984 12.5198 4.27984 12.9398C4.99984 13.3598 5.9865 13.2398 7.05984 12.6198L11.1732 10.2465C12.2465 9.6265 12.8398 8.83316 12.8398 7.99983C12.8398 7.1665 12.2465 6.37316 11.1732 5.75316L7.05984 3.37983C6.4065 3.0065 5.79317 2.81316 5.2465 2.81316Z"
                        fill="#F87171" />
                </svg>


                <div class="text-2 color-1 ml-8">Ошибка</div>
            </div>




        </div>
    </div>
</template>

<script>

export default {
    name: 'SelecterInterests',
    props: {
        interests: Array
    },
    data() {
        return {

        }
    },
    components: {
    }
}

</script>

<style scoped>
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
}

.color-1 {
    color: #6B7280;
}

.color-2 {
    color: #3B82F6;
}

::-webkit-scrollbar {
    width: 6px;
    margin-right: 5px;
}



/* Handle */
::-webkit-scrollbar-thumb {
    /* border-radius: 999px; */
    border-radius: 10px;
    background: #E5E7EB;
}





.cntr-selecter {
    box-sizing: border-box;
    overflow: scroll;
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    padding: 0px 0px 8px;

    /* position: absolute; */
    width: 210px;
    height: 162px;


    z-index: 14;
}

.wrap__cntr-selecter {
    box-sizing: border-box;
    /* overflow: scroll; */
    overflow-x: hidden;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    /* padding: 0px 0px 8px; */

    position: absolute;
    width: 210px;
    height: 162px;
    left: 0px;
    top: 40px;

    /* White/White */

    background: #FFFFFF;
    /* Gray/200 */

    border: 1px solid #E5E7EB;
    /* Drop Shadow/lg */

    box-shadow: 0px 10px 8px rgba(0, 0, 0, 0.04), 0px 4px 3px rgba(0, 0, 0, 0.1);
    border-radius: 8px;

    z-index: 14;
}

.cntr-selecter-item {
    padding: 8px 12px;
    /* gap: 8px; */
    margin-left: 8px;
    margin-top: 8px;
    display: flex;
    justify-content: left;
    align-items: center;
    width: 80%;
    height: 32px;
    cursor: pointer;
}

.cntr-selecter-item:hover {
    background: #F3F4F6;
    border-radius: 6px;
}

.ml-8 {
    margin-left: 8px;
}
</style>