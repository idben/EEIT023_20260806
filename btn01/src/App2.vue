<script setup>
import MyButton2 from './components/MyButton2.vue'
</script>

<template>
  <div class="container py-3">
    <MyButton2 size="sm">
      <template #default>
        註冊
      </template>
      <template #icon="{ iconClass }">
        <i :class="['fa-solid', 'fa-address-card', iconClass]"></i>
      </template>
    </MyButton2>

    <br>

    <MyButton2>
      <template #icon="{ iconClass }">
        <i :class="['fa-solid', 'fa-right-to-bracket', iconClass]"></i>
      </template>
      登入
    </MyButton2>

    <br>

    <MyButton2 size="lg">
      加入我的最愛
      <template v-slot:icon="{ iconClass }">
        <i :class="['fa-solid', 'fa-bookmark', iconClass]"></i>
      </template>
    </MyButton2>

  </div>
</template>

<style scoped></style>