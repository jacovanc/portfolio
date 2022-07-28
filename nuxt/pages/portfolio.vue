<template>
  <div class="inner-wrapper blog" v-if="pageData">
	  {{ pageData }}
    <h1>{{ pageData.data.title }}</h1>
    <div class="content" v-html="pageData.data.description">
      
    </div>
    <div class="blog-items" v-if="portfolioItems">
      
    </div>
	</div>
</template>

<script>
export default {
  name: "portfolio",
  data() {
    return {
      pageData: null,
      portfolioItems: null,
    };
  },
  async fetch() { // Fetch used to pre-render data before build
    this.pageData = await this.$axios.$get("/items/portfolio_category");
    this.portfolioItems = await this.$axios.$get("/items/portfolio_item");
  },
};
</script>
