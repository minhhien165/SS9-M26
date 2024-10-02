<template>
  <div>
    <h2>Thêm mới tài khoản</h2>
    <form @submit.prevent="handleSubmit">
      <div>
        <label for="name">Tên:</label>
        <input type="text" id="name" v-model="user.name" />
      </div>

      <div>
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="user.email" />
      </div>

      <div>
        <label for="password">Mật khẩu:</label>
        <input type="password" id="password" v-model="user.password" />
      </div>

      <div>
        <label for="confirmPassword">Nhập lại mật khẩu:</label>
        <input type="password" id="confirmPassword" v-model="confirmPassword" />
      </div>

      <button type="submit">Đăng ký</button>
    </form>
  </div>
</template>

<script setup>
import { ref } from "vue";

const user = ref({
  name: "",
  email: "",
  password: "",
});

const confirmPassword = ref("");

const handleSubmit = () => {
  if (user.value.password !== confirmPassword.value) {
    alert("Mật khẩu và Nhập lại mật khẩu không khớp");
  } else {
    console.log("Thông tin user:", user.value);
    alert("Đăng ký thành công!");
  }
};
</script>

<style>
</style>
