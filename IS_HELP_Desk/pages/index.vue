<template>
  <div class="container-fluid bg">
    <div class="d-flex justify-content-center align-items-center min-vh-100">
      <b-card class="custom-card">
        <b-form-group label="Username">
          <b-form-input placeholder="Enter username or email" style="width: 400px;" />
        </b-form-group>
        <b-form-group label="Password">
          <b-form-input type="password" placeholder="Enter password" style="width: 400px;" />
        </b-form-group>
        <b-button class="mt-3" type="submit" variant="success" style="width: 400px;" href="/home">
          Login
        </b-button>
        <div class="mt-4 py-2" style="border: 1px solid rgb(206,212,218); padding: 10px; border-radius: 5px; text-align: center; height: 40px;">
          New to IS halp desk ?<b-link variant="primery"> Create account</b-link>
        </div>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style>
.custom-card {
  max-width: 500px;
  margin: 0 auto;
  /* Center horizontally */
  transform: translateY(-50%);
  border: 1px solid rgb(175, 175, 175);
  /* เพิ่มเส้นขอบสีดำขนาด 1px */
  border-radius: 15px;
  /* ปรับรูปร่างของเส้นขอบเป็นรูปสี่เหลี่ยมทรงกลม */
}

.bg {
  background: linear-gradient(45deg, #84BFDD, #FFF7CF);
}</style>
