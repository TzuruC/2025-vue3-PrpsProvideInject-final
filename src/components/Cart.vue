<template>
  <div class="col-md-4">
    <h2 class="mb-3">購物車</h2>
    <ul class="list-group mb-3">
      <li
        class="list-group-item d-flex justify-content-between align-items-center"
        v-for="item in carts"
        :key="item.id"
      >
        <div>
          <h6 class="my-0">{{ item.name }}</h6>
          <small class="text-muted">數量：{{ item.quantity }}</small>
        </div>
        <div>
          <span class="text-muted">${{ item.price }}</span>
          <button class="btn btn-sm btn-outline-danger ms-2">移除</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup>
const props = defineProps({
  carts: {
    type: Array,
    require: true,
  },
})
</script>

<style lang="scss" scoped></style>
