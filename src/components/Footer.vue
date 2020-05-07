<template>
	<div>
		<nav class="navbar is-primary is-fixed-top" id="#navbar">
			<div class="navbar-brand">
				<router-link to="/#" @click.native="$scrollToTop" class="navbar-item dog"/>
				<div class="navbar-burger burger" @click="showNav = !showNav"
					 :class="{ 'is-active': showNav }"
					 style="color: white">
					<span></span>
					<span></span>
					<span></span>
				</div>
			</div>
			<div class="navbar-end navbar-menu" :class="{ 'is-active': showNav }">
				<router-link to="/about" class="navbar-item">
					<b-icon icon="information-outline"/>&nbsp;
					<span> About </span>
				</router-link>
			</div>
		</nav>
	</div>
</template>

<script>
	import BIcon from "buefy/src/components/icon/Icon";

	export default {
		name: "Navbar",
		components: {BIcon},
		data() {
			return {
				showNav: false,
			}
		}
	}
</script>

<style scoped lang="scss">
	.dog {
		width: 64px;
		height: 4rem;
		background: url('../assets/cpu.svg') no-repeat center;
		background-size: 48px;
		fill: white;
	}

</style>