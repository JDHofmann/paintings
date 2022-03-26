<template>
	<header id="menu-bar">
		<div id="static-items">
			<span id="logo">Amissa</span>
			<div id="menu-buttons">
				<button
					aria-haspopup="true"
					aria-expanded="false"
					data-toggle="dropdown"
					@click="showMenu"
					class="show-menu"
					:class="isActive ? 'hidden' : 'show'"
				>
					<span></span>
					<span></span>
					<span></span>
					<!-- -
                    <span aria-hidden="true">&#x25be</span> -->
				</button>
				<button
					aria-haspopup="false"
					aria-expanded="true"
					data-toggle="dropdown"
					@click="closeMenu"
					class="hide-menu"
					:class="isActive ? 'show' : 'hidden'"
				>
					<span></span>
					<span></span>
				</button>
			</div>
		</div>
		<div
			id="pop-out"
			:class="isActive ? 'show' : 'hidden'"
			role="menu"
			aria-hidden="true"
		>
			<nav>
				<ul>
					<li @click="closeMenu">
						<nuxt-link to="/"> home </nuxt-link>
					</li>
					<li @click="closeMenu">
						<nuxt-link to="/projects"> projects </nuxt-link>
					</li>
					<li @click="closeMenu">
						<nuxt-link to="/about"> about </nuxt-link>
					</li>
					<li @click="closeMenu">
						<nuxt-link to="/contact"> contact </nuxt-link>
					</li>
				</ul>
			</nav>
		</div>
	</header>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			isActive: false,
		};
	},
	methods: {
		showMenu() {
			this.isActive = true;
			return this.isActive;
		},
		closeMenu() {
			this.isActive = false;
			return this.isActive;
		},
	},
	mounted() {
		// console.log('mounted')
	},
};
</script>

<style scoped lang="scss">
header {
	border-bottom: 1px solid;
	margin: 0 1rem;
}
button {
	background: none;
	width: 35px;
	height: 35px;
	font-size: 15px;
	padding: 5px;
	&.show {
		display: flex;
		flex-direction: column;
		justify-content: space-evenly;
	}
	&.show-menu {
		span {
			display: block;
			height: 1px;
			line-height: 0px;
			background: #ffffff;
		}
	}
	&.hide-menu {
		&.show {
			display: block;
		}
		span {
			display: block;
			height: 1px;
			line-height: 0px;
			background: #ffffff;
		}
		span:nth-child(1) {
			transform: rotate(45deg);
		}
		span:nth-child(2) {
			transform: rotate(-45deg);
		}
	}
}
#menu-bar {
	background: $eight;
	color: $text-light;
	margin: 0;
	padding: 0 1rem;
	#pop-out {
		ul li {
			font-size: 18px;
		}
	}
	nav {
		background: $eight;
		padding: 5rem 0.5rem;
		color: $text-light;
	}
}
</style>
