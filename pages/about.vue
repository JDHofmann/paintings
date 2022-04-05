<template>
	<main>
		<div class="hero">
			<h1>ABOUT THE ROOM TO GROW PROJECT</h1>
		</div>
		<section>
			<h2>Project aims</h2>
			<p>
				I hope that this project might give patients and their families
				an emotional outlet, as well as a new way to think about their
				illness or symptoms. I also hope that showcasing patient stories
				in this way will inspire medical professionals to become better
				listeners and to approach patient encounters with a more open
				mind. Ultimately, I aim to see what happens when patients are
				allowed to freely and candidly describe their experiences and
				what can happen when they get help externalizing what they want
				others to know.
			</p>
			<h2>Methods</h2>
			<p>
				Four patients agreed to speak candidly with me about their
				experience with chronic illness. Each conversation lasted around
				15-30 minutes and took place over Zoom. During the conversation,
				the patients and I worked together to construct a visual
				representation of their experiences: physical symptoms, medical
				history, relationships, emotional responses, and hopes for the
				future. I spent several weeks dedicated to working on these
				pieces in my home studio (living room). I used acrylic paint on
				canvas. I am endlessly grateful to all four of them and feel
				lucky that they shared their incredible stories with me for this
				project.
			</p>
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
		// console.log(this.photo);
	},
};
</script>
<style scoped>
section,
.hero {
	width: calc(100% - 10vw);
	margin: 0 5vw;
}
h2 {
	font-weight: 700;
	text-decoration: underline;
	padding: 1rem 0;
}
</style>
