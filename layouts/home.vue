<template>
	<!-- <div :class="theme"> -->
	<div class="main-theme" id="home">
		<Header />
		<Nuxt />
		<footer>
			<p>Amissa Brewer-Hofmann 2022</p>
		</footer>
	</div>
</template>

<script>
import { mapState } from "vuex";

export default {
	// computed: {
	// 	...mapState(["theme"]),
	// },
};
</script>

<style scoped lang="scss">
body {
	background: $eight;
}

button {
	border: 5px solid #ffffff;
}
main {
	min-height: none;
	margin: -1px 0;
}
</style>
