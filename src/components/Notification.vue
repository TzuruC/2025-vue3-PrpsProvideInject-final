<template>
  <div class="position-fixed top-0 end-0 p-3" style="z-index: 1050" v-if="notificationState.isShow">
    <!-- 比較  v-if="notificationState.isShow" 放在父元件判斷的差異 -->
    <div class="toast show align-items-center text-white bg-success border-0">
      <div class="d-flex">
        <div class="toast-body">{{ notificationState.message }}</div>
        <button type="button" class="btn-close btn-close-white me-2 m-auto"></button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue'

const notificationState = inject('notificationState')
</script>

<style lang="scss" scoped></style>
