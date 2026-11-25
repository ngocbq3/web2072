<script setup>
import { ref } from "vue";
const student = ref({
  id: 1,
  name: "Nguyễn Văn A",
  class: "CNTT 1",
});
</script>
<template>
  <div>
    <h3>{{ student.name }}</h3>
    <p>Lớp: {{ student.class }}</p>
    <p>Mã SV: {{ student.id }}</p>
  </div>
</template>
