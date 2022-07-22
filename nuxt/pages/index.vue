<template>
	<div class="inner-wrapper about" v-if="pageData">
		<h1>{{ pageData.data.title }}</h1>
		<div class="profile-img-container">
			<img class="profile-img" :src="$config.API_BASE_URL + '/assets/' + pageData.data.main_image" alt="This is a picture of me - please don't spend too much time looking at it.">
		</div>
		<div class="main_content" v-html="pageData.data.main_content">{{ pageData.data.main_content }}</div>
	</div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      pageData: null
    }
  },
  async fetch() {
    this.pageData = await this.$axios.$get('/items/Homepage');
  },
};
</script>

<style scoped>
  .about .profile-img-container {
		width: 250px;
		height: 250px;
		overflow: hidden;
		margin-left: 15px;
		border-radius: 50%;
		float: right;
	}
	.about .profile-img {
		width: 100%;
	}
	@media screen and (max-width: 500px) {
		.about .profile-img-container {
			float: none;
			width: 250px;
			margin: 0 auto;
			display: block;
		}
	}
</style>