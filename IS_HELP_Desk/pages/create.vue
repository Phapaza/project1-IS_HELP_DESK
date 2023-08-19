<template>
  <div class="container-fluid bg">
    <div class="d-flex justify-content-center align-items-center min-vh-100">
      <b-card class="custom-card container-fluid" style="border-radius: 15px;">
        <div class="text-center">
          <img src="~/assets/images/1.png" class="img-fluid custom-image">
        </div>
        <b-form-group class="text-left" label="Username">
          <b-form-input placeholder="Enter username or email" style="width: 400px;" v-model="username" />
        </b-form-group>
        <b-form-group class="text-left" label="First Name">
          <b-form-input placeholder="Enter First Name" style="width: 400px;" v-model="firstName" />
        </b-form-group>
        <b-form-group class="text-left" label="Last Name">
          <b-form-input placeholder="Enter Last Name" style="width: 400px;" v-model="lastName" />
        </b-form-group>
        <b-form-group class="text-left" label="Status">
          <b-form-select v-model="status" :options="statusOptions" style="width: 400px;" />
        </b-form-group>
        <b-form-group class="text-left" label="ID Student" v-if="status === 'student'">
          <b-form-input v-model="studentId" placeholder="Enter Student ID" style="width: 400px;" />
        </b-form-group>
        <b-form-group class="text-left" label="Password">
          <b-form-input v-model="password" type="password" placeholder="Enter password" style="width: 400px;" />
          <div v-if="password.length > 0 && password.length < 8" class="text-danger">
            Password must be at least 8 characters.
          </div>
        </b-form-group>
        <b-form-group class="text-left" label="Confirm Password">
          <b-form-input v-model="confirmPassword" type="password" placeholder="Enter Confirm Password"
            style="width: 400px;" />
          <div v-if="confirmPassword.length > 0 && password !== confirmPassword" class="text-danger">
            Passwords do not match.
          </div>
        </b-form-group>
        <b-button class="mt-3 mb-4" type="submit" variant="success" style="width: 400px;" :disabled="!formValid"
          @click="handleRegistration">
          Register
        </b-button>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      firstName: '',
      lastName: '',
      password: '',
      confirmPassword: '',
      status: 'student', // ค่าเริ่มต้นเป็น 'student'
      studentId: '',
      statusOptions: [
        { value: 'student', text: 'Student' },
        { value: 'teacher', text: 'Teacher' },
      ],
    };
  },
  computed: {
    passwordMismatch() {
      return this.password !== this.confirmPassword;
    },
    formValid() {
      if (this.status === 'student') {
        return (
          this.username &&
          this.firstName &&
          this.lastName &&
          this.password &&
          this.confirmPassword &&
          this.studentId &&
          !this.passwordMismatch
        );
      } else {
        return (
          this.username &&
          this.firstName &&
          this.lastName &&
          this.password &&
          this.confirmPassword &&
          !this.passwordMismatch
        );
      }
    },
  },
  methods: {
    handleRegistration() {
      if (this.formValid) {
        // Perform registration logic here
        // For example, you can navigate to the home page
        this.$router.push('/home');
      }
    },
  },
};
</script>

<style>
.custom-card {
  max-width: 470px;
  margin: 0 auto;
  border: 1px solid rgb(175, 175, 175);
}

.custom-image {
  width: 400px;
  display: block;
  margin: 0 auto;
}

.bg {
  background: linear-gradient(45deg, #84BFDD, #FFF7CF);
}
</style>
