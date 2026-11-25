<script setup>
import { ref } from "vue";

const students = ref([
  { MSSV: 1, name: "Nguyễn Văn Long", email: "longnv@gmail.com" },
  { MSSV: 2, name: "Trần Long Ẩn", email: "antl@gmail.com" },
  { MSSV: 3, name: "Lê Quang Thọ", email: "tholq@gmail.com" },
  { MSSV: 4, name: "Bùi Xuân Diệu", email: "dieubx@gmail.com" },
  { MSSV: 5, name: "Nguyễn Tiến Anh", email: "anhnt@gmail.com" },
]);
</script>
<template>
  <div>
    <ul>
      <li v-for="{MSSV, name, email} in students" :key="MSSV">
        {{ MSSV }} - {{ name }} - {{ email }}
      </li>
    </ul>
  </div>
</template>
