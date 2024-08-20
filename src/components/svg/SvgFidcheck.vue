<template>
    <svg class="svg_fid" xmlns="http://www.w3.org/2000/svg" width="92" height="43" viewBox="0 0 92 43" fill="none">
        <rect x="36.5" y="12.5" width="19" height="19" rx="4.5" :stroke="is_check ? '#3B82F6': error_export ? '#F87171': '#6B7280'" />
        <!-- <path d="M92 0H93V-1H92V0ZM0 1H92V-1H0V1ZM91 0V43H93V0H91Z" fill="#E5E7EB"
                                    mask="url(#path-1-inside-1_58_17791)" /> -->
    </svg>
</template>


<script>
export default {
    props: {
        is_check: Boolean,
        error_export: Boolean,
    }
}
</script>

<style scoped>
.svg_fid {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
}
</style>

