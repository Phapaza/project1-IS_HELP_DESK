<template>
  <div class="container-fluid">
    <div class="d-flex justify-content-center align-items-center min-vh-100">

      <div class="min-vh-100 col-8" md="auto">
        <b-calendar class="border rounded p-2" v-model="value" @context="onContext" block locale="en-US"></b-calendar>
        <b-button class="mt-3 ml-5" type="submit" variant="success" style="width: 400px" href="/login">
          Login Page
        </b-button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      value: "",
      context: null,
    };
  },
  methods: {
    onContext(ctx) {
      this.context = ctx;
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

body {
  background: linear-gradient(45deg, #84bfdd, #fff7cf);
}
</style>
