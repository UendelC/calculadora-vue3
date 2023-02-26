<script lang="ts" setup>
import Key from './Key.vue';

const keys = [
    { value: 'CE', type: 'clear'},
    { value: 'C', type: 'clear-back' },
    { value: '%', type: 'regular' },
    { value: '÷', type: 'operator' },
    { value: '7', type: 'regular' },
    { value: '8', type: 'regular' },
    { value: '9', type: 'regular' },
    { value: 'x', type: 'operator' },
    { value: '4', type: 'regular' },
    { value: '5', type: 'regular' },
    { value: '6', type: 'regular' },
    { value: '-', type: 'operator' },
    { value: '1', type: 'regular' },
    { value: '2', type: 'regular' },
    { value: '3', type: 'regular' },
    { value: '+', type: 'operator' },
    { value: '+/-', type: 'sign' },
    { value: '0', type: 'regular' },
    { value: '.', type: 'regular' },
    { value: '=', type: 'equal' },
];

</script>

<template>
    <div class="keyboard-body">
        <Key
            v-for="(key, index) in keys"
            :key="index"
            :value="key.value"
            :type="key.type"
            @click="$emit('key-clicked', { value: key.value, type: key.type })"
        />
    </div>
</template>

<style scoped>
.keyboard-body {
    display: grid;
    grid-template-columns: repeat(4, 64px);
    gap: 12px;
}
</style>