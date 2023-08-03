<template>
	<header class="header">
		<div class="header__container">
			<div class="header__text-wrapper">
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
							<a href="#">About</a>
						</li>
						<li class="navigation-list__item">
							<a href="#">Location</a>
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
<script>
export default {
	name: "HeaderComponent"
}
</script>
<style lang="scss">
.header {

	// .header__container
	&__container {
		height: 96px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-family: 'Space Mono', monospace;
	}

	// .header__text-wrapper
	&__text-wrapper {
		display: flex;
		align-items: center;
	}

	// .header__logo
	&__logo {
	}

	// .header__navigation
	&__navigation {
		margin-left: 58px;
	}

	// .header__navigation-list
	&__navigation-list {
		display: flex;
	}

	// .header__get-scootin
	&__get-scootin {
	}
}
</style>