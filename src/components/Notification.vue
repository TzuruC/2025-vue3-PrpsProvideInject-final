<template>
  <div class="position-fixed top-0 end-0 p-3" style="z-index: 1050">
    <div
      class="toast show align-items-center text-white border-0 mb-1"
      v-for="toast in notificationState.toasts"
      :key="toast.id"
      :class="{
        'bg-success': toast.type === 'success',
        'bg-danger': toast.type === 'danger',
      }"
    >
      <div class="d-flex">
        <div class="toast-body">{{ toast.message }}</div>
        <button
          type="button"
          class="btn-close btn-close-white me-2 m-auto"
          @click="removeToast(toast.id)"
        ></button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { inject } from 'vue'

const notificationState = inject('notificationState')

function removeToast(id) {
  const index = notificationState.toasts.findIndex((t) => t.id === id)
  if (index !== -1) {
    notificationState.toasts.splice(index, 1)
  }
}
</script>

<style lang="scss" scoped></style>
