<template>
	<div class="main-wrapper" id="touchsurface">
		<div id="nav">
			<div class="inner-wrapper">
        <NuxtLink to="/" class="site-title">Jaco van Cranenburgh</NuxtLink>
				<div class="links">
          <NuxtLink to="/">About</NuxtLink>
					<!-- <router-link to="/portfolio">Portfolio</router-link> | -->
					<NuxtLink to="/blog">Blog</NuxtLink> 
					<!-- <a :href="`${urlCV}`" target="_blank">CV</a> -->
				</div>
				<div class="clear"></div>
			</div>
		</div>
		<div class="outer-wrapper">
      <Nuxt/>
			<!-- <div class="back-to-top" v-if="largeContent" v-on:click="backToTop"></div> -->
		</div>
	</div>
</template>