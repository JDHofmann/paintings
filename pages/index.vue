<template>
	<main id="home-page">
		<!-- <div class="hero">
			<h1>Home</h1>
		</div> -->

		<img src="/flowers.png" />
	</main>
</template>

<script>
import { mapState, mapActions } from "vuex";

export default {
	name: "IndexPage",
	layout: "home",
	computed: {
		...mapState(["projects", "theme"]),
	},
	methods: {
		...mapActions(["changeTheme"]),
	},
	mounted() {
		console.log(this.projects);
	},
};
</script>

<style scoped lang="scss">
body {
	background: $background;
}
button {
	border: 5px solid #ffffff;
}
main {
	margin: 0;
	padding: 0;
	min-height: auto;
	background: $background;
}
img {
	width: 100%;
}
</style>
