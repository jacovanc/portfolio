<template>
	<a v-if="BlogPost" :href="BlogPost.link" class="blog-item" target="_blank">
		<h2 class="title">{{ BlogPost.title }}</h2>
		<span>{{ BlogPost.platform }}</span> |
		<span>{{ BlogPost.date }}</span>
		<div class="description">
			{{ BlogPost.description }}
		</div>
	</a>
</template>

<script>
	export default {
		props: {
			BlogPost: {
				type: Object,
				required: true
			}
		},
	}
</script>

<style scoped>
	a.blog-item,
	a.blog-item:visited,
	a.blog-item:hover,
	a.blog-item:focus,
	a.blog-item:hover, 
	a.blog-item:active { 
		text-decoration: none; color:inherit; 
	}
	.blog-item {
		text-decoration: none;
		font-size: 15px;
		margin-bottom: 15px;
		display: inline-block;

		transition: 0.2s ease;

		border-left: 1px solid grey;
		padding-left: 10px;
	}
	.blog-item:hover {
		transform: scale(1.01);
	}
	.blog-item .title {
		margin: 0;
	}
	.blog-item span {
		font-style: italic;
	}
	.blog-item .description {
		margin-top: 3px;
	}
</style>
