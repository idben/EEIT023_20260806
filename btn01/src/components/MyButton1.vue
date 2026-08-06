<script setup></script>

<template>
  <button class="btn btn-danger mb-1 btn-color1">
    <slot name="icon"></slot>
    <slot>預設文字</slot>
  </button>
</template>

<style scoped>
.btn-color1 {
  --bs-btn-color: #fff;
  --bs-btn-bg: #7c3aed;
  --bs-btn-border-color: #7c3aed;
  --bs-btn-hover-color: #fff;
  --bs-btn-hover-bg: #510fba;
  --bs-btn-hover-border-color: #6d28d9;
  --bs-btn-active-color: #fff;
  --bs-btn-active-bg: #5b21b6;
  --bs-btn-active-border-color: #5b21b6;
  --bs-btn-disabled-color: #fff;
  --bs-btn-disabled-bg: #c4b5fd;
  --bs-btn-disabled-border-color: #c4b5fd;
}
</style>