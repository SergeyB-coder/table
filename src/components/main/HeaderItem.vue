<template>
    <div @click="is_sorted = !is_sorted" class="cur_p">
        <div v-if="!is_sorted" class="main__text_menu main__column">{{ text }}</div>
        <div v-if="is_sorted" class="main__text_menu-selected main__column">{{ text }}
            <span class="ml-14">
                <svg width="8" height="8" viewBox="0 0 8 8" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M3.99986 8.26636e-05C3.86725 8.2652e-05 3.74007 0.0527607 3.6463 0.146529C3.55254 0.240297 3.49986 0.367474 3.49986 0.500083L3.49986 6.29308L1.35386 4.14608C1.30737 4.09959 1.25218 4.06272 1.19144 4.03756C1.1307 4.0124 1.0656 3.99945 0.999857 3.99945C0.934113 3.99945 0.869013 4.0124 0.808273 4.03756C0.747534 4.06272 0.692345 4.09959 0.645857 4.14608C0.599369 4.19257 0.562492 4.24776 0.537333 4.3085C0.512174 4.36924 0.499225 4.43434 0.499225 4.50008C0.499225 4.56583 0.512174 4.63093 0.537333 4.69167C0.562492 4.75241 0.599369 4.80759 0.645857 4.85408L3.64586 7.85408C3.6923 7.90065 3.74748 7.93759 3.80822 7.9628C3.86897 7.988 3.93409 8.00098 3.99986 8.00098C4.06562 8.00098 4.13074 7.988 4.19149 7.9628C4.25224 7.93759 4.30741 7.90065 4.35386 7.85408L7.35386 4.85408C7.44774 4.7602 7.50049 4.63286 7.50049 4.50008C7.50049 4.36731 7.44774 4.23997 7.35386 4.14608C7.25997 4.0522 7.13263 3.99945 6.99986 3.99945C6.86708 3.99945 6.73974 4.0522 6.64586 4.14608L4.49986 6.29308L4.49986 0.500083C4.49986 0.367474 4.44718 0.240297 4.35341 0.146529C4.25964 0.0527608 4.13247 8.26752e-05 3.99986 8.26636e-05Z" fill="#006AFF"/>
                </svg>
            </span>
        </div>
    </div>
</template>

<script>
    
    export default {
        data() {
            return {
                is_sorted: false
            }
        },
        props: {
            text: String,
        }
        
    }

</script>

<style scoped>
.cur_p {
    cursor: pointer;
}
.ml-14 {
    margin-left: 14px;
}
.main__column {
    width: 15vw;
}
.main__text_menu {
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

.main__text_menu-selected {
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
</style>