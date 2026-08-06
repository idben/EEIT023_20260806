<script setup></script>

<template>
    <div class="container py-5">
        <div class="card mw500px">
            <div class="card-header bg-primary text-white text-center">
                <!-- 標題與統計 -->
                <h3 class="fw-bold">待辧事項清單</h3>

                <div class="d-flex gap-3 justify-content-center">
                    <div>
                        <div class="fs-3 fw-bold">3</div>
                        <div class="opacity-75">總計</div>
                    </div>
                    <div>
                        <div class="fs-3 fw-bold">1</div>
                        <div class="opacity-75">已完成</div>
                    </div>
                    <div>
                        <div class="fs-3 fw-bold">2</div>
                        <div class="opacity-75">待處理</div>
                    </div>
                </div>




            </div>
            <div class="card-body">
                <!-- 輸入區 -->
                <div class="input-group">
                    <input type="text" class="form-control" placeholder="新增待辦事項...">
                    <button class="btn btn-primary">新增</button>
                </div>
                <!-- 篩選按鈕 -->
                <div class="d-flex gap-2 my-2">
                    <button class="btn btn-light btn-primary  btn-sm rounded-pill">全部</button>
                    <button class="btn btn-light btn-sm rounded-pill">待處理</button>
                    <button class="btn btn-light btn-sm rounded-pill">已完成</button>
                </div>
                <!-- 待辦事項區 -->
                <ul class="list-group">
                    <li class="list-group-item d-flex gap-1 align-items-center">
                        <span class="check-circle">
                            <i class="fa-solid fa-check"></i>
                        </span>
                        <span class="completed-text">學習 Vue 3 基礎語法</span>
                        <div class="btn btn-outline-danger btn-sm ms-auto">
                            <i class="fa-solid fa-xmark"></i>
                        </div>
                    </li>
                    <li class="list-group-item d-flex gap-1 align-items-center">
                        <span class="check-circle">
                            <i class="fa-solid fa-check"></i>
                        </span>
                        <span>學習 Vue 3 基礎語法</span>
                        <div class="btn btn-outline-danger btn-sm ms-auto">
                            <i class="fa-solid fa-xmark"></i>
                        </div>
                    </li>
                    <li class="list-group-item d-flex gap-1 align-items-center">
                        <span class="check-circle">
                            <i class="fa-solid fa-check"></i>
                        </span>
                        <span>學習 Vue 3 基礎語法</span>
                        <div class="btn btn-outline-danger btn-sm ms-auto">
                            <i class="fa-solid fa-xmark"></i>
                        </div>
                    </li>
                </ul>
            </div>
            <div class="card-footer d-flex align-items-center">
                <!-- 其他功能 -->
                <span>2 項待處理</span>
                <div class="btn btn-danger btn-sm ms-auto">清除已完成</div>
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

.completed-text {
    text-decoration: line-through;
    color: #aaa;
}
</style>