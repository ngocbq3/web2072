<script setup>
const message = "Chào mừng đến với VueJS";
const imageURL =
  "https://www.techone.vn/wp-content/uploads/2026/09/iphone-18-pro-02-1-1.webp";

function show() {
  alert("Hello");
}

//danh sách sinh viên
const students = [
  { id: 1, name: "Nguyễn Văn Long", className: "Js cơ bản" },
  { id: 2, name: "Nguyễn Văn An", className: "Vuejs" },
  { id: 3, name: "Nguyễn Văn Sung", className: "Front-end Framework" },
  { id: 4, name: "Nguyễn Văn Văn", className: "Laravel" },
];
</script>

<template>
  <h1>{{ message }}</h1>
  <button class="btn btn-primary" @click="show">Click</button>

  <div>
    <img :src="imageURL" width="300" alt="" />
  </div>

  <div class="container mt-5">
    <div class="row">
      <div class="col-md-4 mt-2" v-for="stu in students">
        <div class="card">
          <div class="card-title">Name: {{ stu.name }}</div>
          <div class="card-text">
            <p>ID: {{ stu.id }}</p>
            <p>ClassName: {{ stu.className }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
h1 {
  color: red;
  text-align: center;
}
</style>
