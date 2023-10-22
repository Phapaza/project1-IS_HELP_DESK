<template>
  <div class="container-fluid bg">
    <div class="d-flex justify-content-center align-items-center min-vh-100">
      <b-card class="custom-card container-fluid" style="border-radius: 15px">
        <div class="text-center">
          <img src="~/assets/images/1.png" class="img-fluid custom-image">
        </div>
        <b-form-group class="text-left">
          <b-form-input
            placeholder="Enter username or email"
            style="width: 400px"
          />
        </b-form-group>
        <b-form-group class="text-left">
          <span> Password </span>
          <b-form-input
            type="password"
            placeholder="Enter password"
            style="width: 400px"
          />
        </b-form-group>
        <b-button
          class="mt-3 mb-4"
          type="submit"
          variant="success"
          style="width: 400px"
          href="/test"
        >
          Login
        </b-button>
        <div
          class="text-center"
          style="
            border: 1px solid rgb(206, 212, 218);
            padding: auto;
            border-radius: 5px;
          "
        >
          <a href="#" class="btn">
            <img src="~/assets/images/2.png" height="25px">
            Login with Google</a>
        </div>
      </b-card>
    </div>
  </div>
</template>

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
  background: linear-gradient(45deg, #84bfdd, #fff7cf);
}
</style>
