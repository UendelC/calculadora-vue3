<script setup lang="ts">
defineProps({
    operation: {
        type: String,
        required: true
    },
    result: {
        type: String,
        required: true
    }
})

</script>

<template>
    <div class="visor-body">
        <div class="operation">
            {{ operation }}
        </div>
        <div class="result">
            <span>=</span>
            <p>{{ result }}</p>
        </div>
    </div>
</template>

<style scoped>
.operation {
    font-style: normal;
    font-weight: 400;
    line-height: 140%;
    color: #6b6b6b;
    font-size: 20px;
    align-self: flex-end;
}
.visor-body {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 0px 22px 0px 18px;
    gap: 8px;
    width: 288px;
    height: 86px;
}

.result {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-weight: 400;
    padding: 0px;
    font-size: 36px;
    color: #6b6b6b;
}

p {
    font-size: 36px;
    line-height: 140%;
    color: #ebebeb;
}

span {
    user-select: none;
}
</style>