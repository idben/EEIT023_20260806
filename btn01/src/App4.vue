<script setup>
import MyButton4 from './components/MyButton4.vue'
</script>

<template>
  <!-- 全屬性式的元件設計與使用 -->
  <div class="container py-3">
    <MyButton4 text="註冊" size="sm" :icons="['fa-solid', 'fa-address-card']" />
    <br>
    <MyButton4 text="登入" :icons="['fa-solid', 'fa-right-to-bracket']" />
    <br>
    <MyButton4 text="加入我的最愛" size="lg" :icons="['fa-solid', 'fa-bookmark']" />
  </div>
</template>

<style scoped></style>