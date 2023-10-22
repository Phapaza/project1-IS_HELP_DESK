<template>
  <div>
    <no-ssr>
      <div class="layouts">
        <header>
          <b-navbar class="bgNav" toggleable="lg">
            <b-navbar-brand href="/">
              <img src="@/assets/images/1.png" alt="Event" height="30">
              <span style="color: black; font-size: 16px; font-weight: bold">Event</span>
            </b-navbar-brand>
            <b-collapse id="nav-collapse" is-nav>
              <b-navbar-nav class="ml-auto">
                <b-nav-item style="color: black; font-size: 16px; font-weight: bold">
                  Username
                </b-nav-item>
              </b-navbar-nav>
            </b-collapse>
          </b-navbar>
        </header>
      </div>
    </no-ssr>
    <div class="container-fluid">
      <div class="row">
        <div class="col-8 align-items-center min-vh-100">
          <b-calendar
            v-model="value"
            class="border mt-3 rounded p-2"
            block
            locale="en-US"
            @context="onContext"
          />
        </div>
        <div class="col-4">
          <b-card
            title="Card Title"
            img-src="https://picsum.photos/600/300/?image=25"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem"
            class="mt-3 mb-2"
          >
            <b-card-text>
              Some quick example text to build on the card title and make up the
              bulk of the card's content.
            </b-card-text>
          </b-card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      value: '',
      context: null
    }
  },
  methods: {
    onContext (ctx) {
      this.context = ctx
    }
  }
}
</script>
<style>
body {
  background: linear-gradient(45deg, #84bfdd, #fff7cf);
}
.bgNav {
  background: linear-gradient(45deg, #ffffff, #ffffff);
}
</style>
