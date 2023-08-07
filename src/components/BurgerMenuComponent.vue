<script setup>
</script>
<template>
	<div
		class="burger-menu__wrapper"
		@click="$emit('show-menu')"
	>
		<div class="burger-menu__content">
			<nav class="burger-menu__navigation">
				<ul class="burger-menu__list">
					<li class="burger-menu__item">
						<RouterLink to="/">About</RouterLink>
					</li>
					<li class="burger-menu__item">
						<RouterLink to="/about">Location</RouterLink>
					</li>
					<li class="burger-menu__item">
						<RouterLink to="/careers">Careers</RouterLink>
					</li>
				</ul>
				<a
					href="#"
					class="burger-menu__get-scootin btn"
				>Get Scootin
				</a>
			</nav>
		</div>
	</div>
</template>
<style
	scoped
	lang="scss"
>
.burger-menu {
	// .burger-menu__wrapper
	&__wrapper {
		background-color: rgba(0, 0, 0, 0.8);
		position: absolute;
		height: 100%;
		width: 100vw;
		z-index: 5;
	}

	// .burger-menu__content
	&__content {
		height: 100%;
		width: 75%;
		background: #333A44;

	}

	// .burger-menu__navigation

	&__navigation {
		position: sticky;
		top: 0;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		height: 90vh;
	}

	// .burger-menu__list
	&__list {
		padding-top: 64px;
		margin-left: 32px;
		display: flex;
		flex-direction: column;
		row-gap: 24px;
	}

	// .burger-menu__item
	&__item {
		color: #E5ECF4;
		font-family: 'Space Mono', monospace;
		font-size: 18px;
		font-weight: 700;
		line-height: 25px; /* 138.889% */
	}

	&__get-scootin {
		margin-bottom: 24px;
		align-self: center;
	}
}
</style>