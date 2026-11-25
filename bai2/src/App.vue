<script setup>
import { reactive, ref } from "vue";
import Vidu2 from "./components/Vidu2.vue";

const state = reactive({ count: 0 });

function tang() {
  state.count++;
}

const count = ref(0);

function cong() {
  count.value++;
}

const isLoggedIn = ref(false);

import ListRender from "./components/ListRender.vue";
</script>

<template>
  <div>
    <h2 v-if="isLoggedIn">Chào mừng bạn đã quay trở lại</h2>
    <h2 v-else>Bạn cần đăng nhập vào hệ thống</h2>
    <h2 v-show="isLoggedIn">Ẩn/Hiện bằng v-show</h2>
    <button @click="isLoggedIn = !isLoggedIn">Chuyển trang thái</button>
  </div>

  <ListRender />
  <!-- <h2>Count: {{ state.count }}</h2>
  <button @click="tang">Tang</button>
  <hr />
  <h2>Count 2: {{ count }}</h2>
  <button @click="cong">Tang</button>

  <Vidu2 /> -->
</template>
