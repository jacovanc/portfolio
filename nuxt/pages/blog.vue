<template>
  <div class="inner-wrapper blog" v-if="pageData">
    <h1>{{ pageData.data.title }}</h1>
    <div class="content" v-html="pageData.data.description">
      
    </div>
    <div class="blog-items" v-if="blogs">
      <BlogItem v-for="blog in blogs.data" :key="blog.id" :BlogPost="blog"/>
    </div>
	</div>
</template>

<script>
export default {
  name: "blog",
  data() {
    return {
      pageData: null,
      blogs: null,
    };
  },
  async fetch() { // Fetch used to pre-render data before build
    this.pageData = await this.$axios.$get("/items/blog_category");
    this.blogs = await this.$axios.$get("/items/blog");
  },
};
</script>
