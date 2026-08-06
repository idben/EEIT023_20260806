<script setup>
const props = defineProps({
    modelValue: {
        type: String,
        required: true
    }
})

const emit = defineEmits([
    'update:modelValue',
    'add'
])
</script>

<template>
    <div class="input-group">
        <input type="text" class="form-control" placeholder="新增待辦事項..." :value="modelValue"
            @input="emit('update:modelValue', $event.target.value.trim())">
        <button class="btn btn-primary" @click="emit('add')" :disabled="!modelValue">新增</button>
    </div>
</template>

<style scoped></style>