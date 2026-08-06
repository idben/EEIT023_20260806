<script setup>
import MyButton3 from './components/MyButton3.vue'
</script>

<template>
  <div class="container py-3">
    <MyButton3>
      <template #default>
        註冊
      </template>

    </MyButton3>

    <br>

    <MyButton3>
      <template #icon>
        <i class="fa-solid fa-right-to-bracket"></i>
      </template>
      登入
    </MyButton3>

    <br>

    <MyButton3>
      加入我的最愛
      <template v-slot:icon>
        <i class="fa-solid fa-bookmark"></i>
      </template>
    </MyButton3>

    <br>

    <MyButton3></MyButton3>
  </div>
</template>

<style scoped></style>