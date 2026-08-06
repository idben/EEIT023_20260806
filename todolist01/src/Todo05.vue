<script setup>
import { ref, computed } from 'vue'
import TodoHeader from './components/TodoHeader.vue'
import TodoInput from './components/TodoInput.vue'

const todos = ref([
    { id: 1, text: '學習 Vue 3 基礎語法', completed: true },
    { id: 2, text: '練習 Composition API', completed: false },
    { id: 3, text: '完成待辦清單專案', completed: false },
])

const newTodo = ref('')

const filter = ref('all')

const totalCount = computed(() => todos.value.length)
const completedCount = computed(() =>
    todos.value.filter(t => t.completed).length
)
const remainingCount = computed(() =>
    todos.value.filter(t => !t.completed).length
)
const filteredTodos = computed(() => {
    switch (filter.value) {
        case 'active':
            return todos.value.filter(dodo => !dodo.completed)
        case 'completed':
            return todos.value.filter(dodo => dodo.completed)
        default:
            return todos.value
    }
})

const addTodo = () => {
    if (newTodo.value == '') return;

    todos.value.push({
        id: Date.now(),
        text: newTodo.value,
        completed: false
    })

    newTodo.value = ''
}

const deleteTodo = (id) => {
    const index = todos.value.findIndex((dodo) => dodo.id == id)
    if (index > -1) {
        todos.value.splice(index, 1)
    }
}

const toggleTodo = (id) => {
    const todo = todos.value.find((dodo) => dodo.id == id)
    if (todo) {
        todo.completed = !todo.completed
    }
}

const clearCompleted = function () {
    todos.value = todos.value.filter(dodo => !dodo.completed)
}
</script>

<template>
    <div class="container py-5">
        <div class="card mw500px">
            <TodoHeader :totalCount="totalCount" :completedCount="completedCount" :remainingCount="remainingCount" />
            <div class="card-body">
                <!-- 輸入區 -->
                <TodoInput v-model="newTodo" @add="addTodo" />
                <!-- 篩選按鈕 -->
                <div class="d-flex gap-2 my-2">
                    <button class="btn btn-sm rounded-pill" :class="filter == 'all' ? 'btn-primary' : 'btn-light'"
                        @click="filter = 'all'">全部</button>
                    <button class="btn btn-sm rounded-pill" :class="filter == 'active' ? 'btn-primary' : 'btn-light'"
                        @click="filter = 'active'">待處理</button>
                    <button class="btn btn-sm rounded-pill" :class="filter == 'completed' ? 'btn-primary' : 'btn-light'"
                        @click="filter = 'completed'">已完成</button>
                </div>
                <!-- 待辦事項區 -->
                <ul class="list-group">
                    <li v-for="todo in filteredTodos" :key="todo.id"
                        class="list-group-item d-flex gap-1 align-items-center">
                        <span class="check-circle" :class="{ 'checked': todo.completed }" @click="toggleTodo(todo.id)">
                            <i class="fa-solid fa-check"></i>
                        </span>
                        <span :class="{ 'completed-text': todo.completed }">{{ todo.text }}</span>
                        <button class="btn btn-outline-danger btn-sm ms-auto" @click="deleteTodo(todo.id)">
                            <i class="fa-solid fa-xmark"></i>
                        </button>
                    </li>
                </ul>
            </div>
            <div class="card-footer d-flex align-items-center">
                <!-- 其他功能 -->
                <span>{{ remainingCount }} 項待處理</span>
                <button class="btn btn-danger btn-sm ms-auto" @click="clearCompleted">清除已完成</button>
            </div>
        </div>
    </div>
</template>

<style scoped>
.mw500px {
    max-width: 500px;
}

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