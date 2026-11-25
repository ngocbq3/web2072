<script setup>
const props = defineProps({
  id: Number,
  name: String,
  price: Number,
});

const emit = defineEmits(["delete"]);

function deleteProduct() {
  emit("delete", props.id);
}
</script>

<template>
  <div>
    <h2>{{ name }}</h2>
    <p>Mã sp: {{ id }}</p>
    <p>Giá: {{ price }}</p>
    <button @click="deleteProduct">Xóa sản phẩm</button>
  </div>
</template>
