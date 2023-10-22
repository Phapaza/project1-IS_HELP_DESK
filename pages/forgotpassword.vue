<template>
  <div class="container-fluid bg">
    <div class="d-flex justify-content-center align-items-center min-vh-100">
      <b-card class="custom-card container-fluid" style="border-radius: 15px;">
        <div class="text-center mt-3">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="90"
            height="90"
            fill="currentColor"
            class="bi bi-person-exclamation"
            viewBox="0 0 16 16"
          >
            <path
              d="M11 5a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM8 7a2 2 0 1 0 0-4 2 2 0 0 0 0 4Zm.256 7a4.474 4.474 0 0 1-.229-1.004H3c.001-.246.154-.986.832-1.664C4.484 10.68 5.711 10 8 10c.26 0 .507.009.74.025.226-.341.496-.65.804-.918C9.077 9.038 8.564 9 8 9c-5 0-6 3-6 4s1 1 1 1h5.256Z"
            />
            <path
              d="M16 12.5a3.5 3.5 0 1 1-7 0 3.5 3.5 0 0 1 7 0Zm-3.5-2a.5.5 0 0 0-.5.5v1.5a.5.5 0 0 0 1 0V11a.5.5 0 0 0-.5-.5Zm0 4a.5.5 0 1 0 0-1 .5.5 0 0 0 0 1Z"
            />
          </svg>
        </div>
        <h2 class="text-center mb-2">
          Forgot Password
        </h2> 
        <div class="text-center mx-auto">
            <b-form-group class="text-center">
              <h6>Please enter your Email</h6>
            </b-form-group>
            <b-form-input
              placeholder="Enter your Email"
              trim
              type="email"
              required
            />
        </div>
        <div class="text-center">
          <b-form-group class="mt-1" />
          <div class="text-center">
            <b-button
              type="submit"
              variant="success"
            >
              Submit
            </b-button>
          </div>
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
body {
  background: linear-gradient(45deg, #9ddeff, #fff7cf);
}
</style>
