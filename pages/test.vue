<template>
    <div class="container-fluid">
        <div class="min-vh-100 col-8" md="auto">
            <b-calendar class="border rounded p-2" v-model="value" @context="onContext" block locale="en-US"></b-calendar>
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
body {
    background: linear-gradient(45deg, #84bfdd, #fff7cf);
}
</style>
