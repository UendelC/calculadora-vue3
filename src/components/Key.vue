<script setup lang="ts">
import { computed } from 'vue';

interface KeyTypes {
    regular: string;
    operator: string;
    equal: string;
    'clear-back': string;
    'sign': string;
}

const props = defineProps({
    value: {
        type: String,
        required: true
    },
    type: {
        type: String,
        required: true
    }
});


const computedBackground = computed(() => {
    const types: KeyTypes = {
        regular: 'linear-gradient(180deg, rgba(0, 0, 0, 0.05) 0%, rgba(255, 255, 255, 0.05) 100%), #2D2A37',
        'clear-back': 'linear-gradient(180deg, rgba(0, 0, 0, 0.05) 0%, rgba(255, 255, 255, 0.05) 100%), #2D2A37',
        'sign': 'linear-gradient(180deg, rgba(0, 0, 0, 0.05) 0%, rgba(255, 255, 255, 0.05) 100%), #2D2A37',
        operator: 'linear-gradient(180deg, rgba(0, 0, 0, 0.05) 0.01%, rgba(255, 255, 255, 0.05) 100%), #462878',
        equal: 'linear-gradient(180deg, rgba(0, 0, 0, 0.15) 0%, rgba(255, 255, 255, 0.05) 100%), #7F45E2'
    };

    return types[props.type];
});


const computedStyle = computed(() => {
    return {
        color: props.type === 'clear' ? '#975dfa' : '#ebebeb',
        background: computedBackground.value
    }
})
</script>

<template>
    <div
        class="key-body"
        :style="computedStyle"
    >
        <p>{{ value }}</p>
    </div>
</template>

<style scoped>
.key-body {
    width: 64px;
    height: 64px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 999px;
    box-shadow: 0px 11px 7px rgba(0, 0, 0, 0.01), 0px 7px 7px rgba(0, 0, 0, 0.04), 0px 4px 6px rgba(0, 0, 0, 0.1), 0px 2px 4px rgba(0, 0, 0, 0.26), 0px 0px 2px rgba(0, 0, 0, 0.29), inset 0px 2px 3px rgba(255, 255, 255, 0.06);
}

.key-body:hover {
    box-shadow: 0px 11px 7px rgba(0, 0, 0, 0.01), 0px 7px 7px rgba(0, 0, 0, 0.04), 0px 4px 6px rgba(0, 0, 0, 0.1), 0px 2px 4px rgba(0, 0, 0, 0.26), 0px 0px 2px rgba(0, 0, 0, 0.29), inset 0px 2px 3px rgba(255, 255, 255, 0.06), 0px 0px 0px 2px #975dfa;
}

.key-body:active {
    box-shadow: 0px 11px 7px rgba(0, 0, 0, 0.01), 0px 7px 7px rgba(0, 0, 0, 0.04), 0px 4px 6px rgba(0, 0, 0, 0.1), 0px 2px 4px rgba(0, 0, 0, 0.26), 0px 0px 2px rgba(0, 0, 0, 0.29), inset 0px 2px 3px rgba(255, 255, 255, 0.06), 0px 0px 0px 2px #fa5d5d;
}

p {
    font-style: normal;
    font-weight: 400;
    font-size: 24px;
    line-height: 28px;
    user-select: none;
}
</style>