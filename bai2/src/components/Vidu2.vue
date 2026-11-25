<script setup>
import { ref } from "vue";

const course = ref({
  name: "FrontEnd Framework Vue3",
  level: 3,
  time: 30,
  active: true,
});

//tên khóa học mới
const newName = ref("");
function update() {
  course.value.name = newName.value;
}
</script>
<template>
  <div>
    <h3 :class="[course.active ? 'text-primary' : 'text-danger']">
      {{ course.name }}
    </h3>
    <p>Cấp độ: {{ course.level }}</p>
    <p>Thời gian: {{ course.time }}</p>
    <p>
      {{ course.active ? "Đang mở" : "Đang đóng" }}

      <input type="checkbox" v-model="course.active" />
    </p>

    <div>
      <h3>Câp nhật tên khóa học</h3>
      <input type="text" v-model="newName" id="" />
      <br />
      <button @click="update">Cập nhật</button>
    </div>
  </div>
</template>
