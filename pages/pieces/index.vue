<template>
	<main>
		<div class="hero">
			<h1>PIECES</h1>
		</div>
		<section>
			<ul>
				<ProjectCard
					v-for="project in projects"
					:key="project.id"
					:id="project.id"
					:name="project.name"
					:thumbnail="project.thumbnail"
				/>
			</ul>
		</section>
	</main>
</template>

<script>
import { mapState } from "vuex";

export default {
	name: "Projects",
	computed: {
		...mapState(["projects"]),
	},
	mounted() {
		// console.log("anything", this.projects);
	},
};
</script>
<style scoped>
.hero,
section {
	width: calc(100% - 10vw);
	margin: 0 5vw;
}
ul {
	display: flex;
	gap: 2rem;
	flex-wrap: wrap;
	justify-content: space-evenly;
}
</style>
