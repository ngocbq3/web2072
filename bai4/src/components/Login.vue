<script setup>
import { ref } from "vue";

const email = ref("");
const password = ref("");

const errors = ref({
  email: "",
  password: "",
});

const isValid = ref(true);

function validateForm() {
  const emailRegex = /^[a-zA-Z0-9-]{2,}@[\w]{2,}(\.[a-z]+)+$/;
  if (email.value == "") {
    errors.value.email = "Bạn cần nhập email";
    isValid.value = false;
  } else if (!emailRegex.test(email.value)) {
    errors.value.email = "Email chưa đúng định dạng";
  } else {
    errors.value.email = "";
  }

  if (password.value == "") {
    errors.value.password = "Mật khẩu không được để trống";
    isValid.value = false;
  } else {
    errors.value.password = "";
  }
  return isValid.value;
}

function submitHandle() {
  if (validateForm()) {
    alert("Validate thành công");
  }
}
</script>

<template>
  <div>
    <form action="" method="post" novalidate>
      <div class="form-group">
        <label for="">Email</label>
        <input type="email" v-model="email" id="" />
        <span>{{ errors.email }}</span>
      </div>
      <div class="form-group">
        <label for="">Password</label>
        <input type="password" v-model="password" id="" />
        <span>{{ errors.password }}</span>
      </div>
      <button type="submit" @click.prevent="submitHandle">Login</button>
    </form>
  </div>
</template>
