<script setup>
import { ref, computed } from 'vue'

const price = ref(100)
const quantity = ref(3)
const todos = ref([
    { id: 1, text: '學習 Vue', completed: true },
    { id: 2, text: '完成專案', completed: false },
    { id: 3, text: '準備簡報', completed: false },
])

const totalCount = computed(() => todos.value.length)
const completedCount = computed(() =>
    todos.value.filter(todo => todo.completed).length
)
const remainingCount = computed(() =>
    todos.value.filter(todo => !todo.completed).length
)

const total = computed(() => price.value * quantity.value)
</script>

<template>
    <div>
        單價:
        <input type="number" v-model.number="price">
    </div>
    <div>
        數量:
        <input type="number" v-model.number="quantity">
    </div>
    <div>總價: {{ total }}</div>
    <hr>
    <h3>待辦事項</h3>
    <div>總計: {{ totalCount }} 件</div>
    <div>已完成: {{ completedCount }} 件</div>
    <div>待處理: {{ remainingCount }} 件</div>
</template>

<style scoped></style>