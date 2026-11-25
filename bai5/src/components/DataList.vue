<script setup>
//Định nghĩa 1 danh sách chưa biết trước
defineProps({
  items: { type: Array },
});
</script>
<template>
  <ul>
    <li v-for="(item, index) in items" :key="item.id">
      <!-- Định nghĩa slot và truyền dữ liệu ngược cho cha -->
      <slot name="item" :item="item" :index="index">
        <!-- Dữ liệu mặc định trong slot -->
        <span>{{ item.name }}</span>
      </slot>
    </li>
  </ul>
</template>
