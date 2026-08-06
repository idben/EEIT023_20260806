<script setup>
defineProps({
    modelValue: {
        type: String,
        required: true
    }
})
const emit = defineEmits([
    'update:modelValue'
])
</script>

<template>
    <div class="d-flex gap-2 my-2">
        <button class="btn btn-sm rounded-pill" :class="modelValue == 'all' ? 'btn-primary' : 'btn-light'"
            @click="emit('update:modelValue', 'all')">全部</button>
        <button class="btn btn-sm rounded-pill" :class="modelValue == 'active' ? 'btn-primary' : 'btn-light'"
            @click="emit('update:modelValue', 'active')">待處理</button>
        <button class="btn btn-sm rounded-pill" :class="modelValue == 'completed' ? 'btn-primary' : 'btn-light'"
            @click="emit('update:modelValue', 'completed')">已完成</button>
    </div>
</template>

<style scoped></style>