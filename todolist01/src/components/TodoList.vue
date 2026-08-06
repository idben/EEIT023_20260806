<script setup>
defineProps({
    todos: {
        type: Array,
        required: true
    },
    filter: {
        type: String,
        required: true
    }
})
const emit = defineEmits([
    'toggle',
    'delete'
])
</script>

<template>
    <ul class="list-group">
        <li v-for="todo in todos" :key="todo.id" class="list-group-item d-flex gap-1 align-items-center">
            <span class="check-circle" :class="{ 'checked': todo.completed }" @click="emit('toggle', todo.id)">
                <i class="fa-solid fa-check"></i>
            </span>
            <span :class="{ 'completed-text': todo.completed }">{{ todo.text }}</span>
            <button class="btn btn-outline-danger btn-sm ms-auto" @click="emit('delete', todo.id)">
                <i class="fa-solid fa-xmark"></i>
            </button>
        </li>
    </ul>
</template>

<style scoped>
.check-circle {
    width: 24px;
    height: 24px;
    border: 2px solid #ddd;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    font-size: 12px;
}

.check-circle.checked {
    background: #51cf66;
    border-color: #51cf66;
    color: white;
}

.completed-text {
    text-decoration: line-through;
    color: #aaa;
}
</style>