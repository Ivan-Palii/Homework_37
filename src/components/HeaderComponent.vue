<script setup>
const props = defineProps({
	showMenuState: {
		type: Boolean,
		required: true
	}
})
</script>
<template>
	<header class="header">
		<div class="header__container">
			<div class="header__text-wrapper">
				<div
					class="header__menu-burger"
					:class="{'header__menu-burger_active':showMenuState}"
					@click="$emit('show-menu')"
				></div>
				<a
					href="#"
					class="header__logo"
				>
					<img
						src="../assets/logo.svg"
						alt="#"
						title="#"
					>
				</a>
				<nav class="header__navigation">
					<ul class="header__navigation-list navigation-list">
						<li class="navigation-list__item">
							<RouterLink to="/">About</RouterLink>
						</li>
						<li class="navigation-list__item">
							<RouterLink to="/about">Location</RouterLink>
						</li>
						<li class="navigation-list__item">
							<a href="#">Careers</a>
						</li>
					</ul>
				</nav>
			</div>
			<a
				href="#"
				class="header__get-scootin btn"
			>Get Scootin
			</a>
		</div>
	</header>
</template>
<style lang="scss">
@import "../assets/variables.scss";

.header {

	// .header__container
	&__container {
		height: 96px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-family: 'Space Mono', monospace;
		@media (max-width: $mobile) {
			justify-content: center;
			position: relative;
			height: 64px;
		}
	}

	// .header__text-wrapper
	&__text-wrapper {
		display: flex;
		align-items: center;

	}

	// .header__menu-burger
	&__menu-burger {

		width: 20px;
		height: 4px;
		position: absolute;
		left: 32px;
		background-color: #FCB72B;
		display: none;
		transition: .3s;
		@media (max-width: $mobile) {
			display: block;
		}

		&:before,
		&:after {
			content: '';
			width: 20px;
			height: 4px;
			background-color: #FCB72B;
			position: absolute;
			transition: .3s;
			transform-origin: right;
		}

		&:before {
			top: -6px;
		}

		&:after {
			top: 6px;
		}

		&_active {
			background-color: transparent;

			&:before {
				transform: rotate(-45deg);
				top: -7px;
			}
			&:after {
				transform: rotate(45deg);
				top: 7px;
			}
		}


	}

	// .header__logo
	&__logo {

	}

	// .header__navigation
	&__navigation {
		margin-left: 58px;
		@media (max-width: $mobile) {
			display: none;
		}
	}

	// .header__navigation-list
	&__navigation-list {
		display: flex;
	}

	// .header__get-scootin
	&__get-scootin {
		@media (max-width: $mobile) {
			display: none;
		}
	}
}
</style>