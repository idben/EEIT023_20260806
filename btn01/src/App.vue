<script setup>
import MyButton1 from './components/MyButton1.vue'
</script>

<template>
  <div class="container py-3">
    <MyButton1>
      註冊
      <template #icon>
        <i class="fa-solid fa-address-card"></i>
      </template>
    </MyButton1>

    <br>

    <MyButton1>
      <template #icon>
        <i class="fa-solid fa-right-to-bracket"></i>
      </template>
      登入
    </MyButton1>

    <br>

    <MyButton1>
      加入我的最愛
      <template v-slot:icon>
        <i class="fa-solid fa-bookmark"></i>
      </template>
    </MyButton1>

  </div>
</template>

<style scoped></style>