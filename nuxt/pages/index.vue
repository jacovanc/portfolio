<template>
  <div v-if="pageData">
    <NuxtLink to="/blogs">Blogs</NuxtLink>
    Test
    {{pageData.data}}
  </div>
</template>

<script>
export default {
  name: "IndexPage",
  data() {
    return {
      pageData: null,
    };
  },
  async fetch() {
    this.pageData = await this.$axios.$get('/items/Homepage');
  },
};
</script>
