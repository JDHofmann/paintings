<template>
	<main>
		<div class="hero">
			<h1>ABOUT THE ARTIST</h1>
		</div>
		<section>
			<p>{{ biography }}</p>
		</section>
		<section>
			<img :src="photo.url" />
		</section>
	</main>
</template>

<script>
import { mapState } from "vuex";

export default {
	computed: {
		...mapState({
			photo: (state) => state.author[0].photo,
			biography: (state) => state.author[0].biography,
		}),
	},

	mounted() {
		// console.log(this.email);
		// this.email = this.author[0].email;
		// this.links = this.author[0].links;
	},
};
</script>
<style scoped>
.hero,
section {
	width: calc(100% - 10vw);
	margin: 0 5vw;
}
img {
	max-width: 100%;
	margin: 2rem 0;
}
</style>
