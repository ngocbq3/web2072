<script setup>
import { ref } from "vue";
const content = ref("");
const language = ref("");
const hobies = ref([]);

import Login from "./components/Login.vue";
</script>

<template>
  <Login />

  <hr />
  <div>
    <textarea v-model="content" cols="20" rows="5" placeholder="Nội nội dung" />
    <p>
      {{ content }}
    </p>
  </div>
  <hr />
  <div>
    <label for="">Chọn quốc gia</label>
    <select v-model="language" id="">
      <option value="Việt Nam">Việt Nam</option>
      <option value="Pháp">Pháp</option>
      <option value="Nhật">Nhật</option>
      <option value="Anh">Anh</option>
      <option value="Mỹ">Mỹ</option>
    </select>
    <p>Bạn đã chọn: {{ language }}</p>
  </div>
  <hr />
  <div>
    hãy chọn sở thích của bạn: <br />
    <input type="checkbox" v-model="hobies" value="Bóng đá" id="" /> Bóng đá
    <br />
    <input type="checkbox" v-model="hobies" value="Ca nhạc" id="" /> Ca nhạc
    <br />
    <input type="checkbox" v-model="hobies" value="Xem phim" id="" /> Xem phim
    <br />

    <p>Bạn đã chọn: {{ hobies.join(", ") }}</p>
  </div>
</template>
