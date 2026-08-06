<script setup>
defineProps({
    totalCount: {
        type: Number,
        required: true
    },
    completedCount: {
        type: Number,
        required: true
    },
    remainingCount: {
        type: Number,
        required: true
    }
})
</script>

<template>
    <div class="card-header bg-primary text-white text-center">
        <!-- 標題與統計 -->
        <h3 class="fw-bold">待辧事項清單</h3>

        <div class="d-flex gap-3 justify-content-center">
            <div>
                <div class="fs-3 fw-bold">{{ totalCount }}</div>
                <div class="opacity-75">總計</div>
            </div>
            <div>
                <div class="fs-3 fw-bold">{{ completedCount }}</div>
                <div class="opacity-75">已完成</div>
            </div>
            <div>
                <div class="fs-3 fw-bold">{{ remainingCount }}</div>
                <div class="opacity-75">待處理</div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>