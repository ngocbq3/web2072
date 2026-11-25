<script setup>
const emit = defineEmits(["sayHello"]);

function message() {
  emit("sayHello", "Xin chào node Cha");
}
</script>

<template>
  <div>
    <button @click="message">Gọi dữ liệu</button>
  </div>
</template>
