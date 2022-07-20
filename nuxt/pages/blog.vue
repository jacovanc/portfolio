<template>
  <div>
    <NuxtLink to="/">Home</NuxtLink>
  </div>
</template>

<script>
export default {
  name: "BlogsPage",
  data() {
    return {
      pageData: null,
    };
  },
  async fetch() { // Fetch used to pre-render data before build
    this.pageData = await this.$axios.$get("/items/Homepage");
  },
  methods: {
    async fetchNewData() {
      console.log("hit");
    }
  },
};
</script>
