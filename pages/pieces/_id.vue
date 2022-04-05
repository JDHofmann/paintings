<template>
	<main>
		<section>
			<div id="project-images">
				<div v-for="(img, i) in project.images" :key="i">
					<img :src="img.path" :alt="img.title" />
				</div>
			</div>
		</section>
		<div class="hero">
			<h1>{{ project.name }}</h1>
			<p>{{ project.subhead }}</p>
		</div>
		<section>
			<p class="description">{{ project.description }}</p>
		</section>
	</main>
</template>

<script>
import { mapState } from "vuex";

export default {
	computed: {
		...mapState(["projects"]),
		project() {
			return this.projects.find((p) => p.id == this.$route.params.id);
		},
	},

	mounted() {},
};
</script>

<style scoped lang="scss">
#project-images {
	display: flex;
	justify-content: space-evenly;
	flex-wrap: wrap;
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
	align-items: end;
	justify-items: center;
	grid-column-gap: 1rem;
	grid-row-gap: 1rem;
	width: 100%;
}
#project-images div {
	// width: 80%;
	// padding: 1rem 2rem 2rem;
}
#project-images img {
	width: 100%;
	// border: 1px solid;
}
h4 {
	padding: 0.5rem 0;
	border-bottom: 1px solid;
}
section,
.hero {
	width: calc(100% - 10vw);
	margin: 0 5vw;
}
.hero {
	padding: 0.5rem 0;
	border-bottom: 1px solid;
	margin-bottom: 2rem;
	p {
		font-style: italic;
	}
}
</style>
