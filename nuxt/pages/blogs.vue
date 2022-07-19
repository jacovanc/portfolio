<template>
  <div>
    <NuxtLink to="/">Home</NuxtLink>
    Test
	{{pageData}}
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
  async fetch() {
    this.pageData = await this.$axios.$get("/items/Homepage");
  },
};
</script>
