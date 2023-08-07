<template>
	<footer class="footer">
		<div class="footer__container">
			<div class="footer__text-wrapper">
				<a
					href="#"
					class="footer__logo"
				>
					<img
						src="../assets/logo_footer.svg"
						alt="#"
						title="#"
					>
				</a>
				<nav class="footer__navigation">
					<ul class="footer__navigation-list navigation-list">
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
			<div class="footer__social-icons social-icons">
				<a
					href="#"
					class="social-icons__item icon-facebook_icon"
				></a>
				<a
					href="#"
					class="social-icons__item icon-twitter_icon"
				></a>
				<a
					href="#"
					class="social-icons__item icon-inst_icon"
				></a>
			</div>
		</div>
	</footer>
</template>
<script>
export default {
	name: "FooterComponent"
}
</script>
<style
	lang="scss"
>
@import "../assets/variables";
.footer {
	margin-top: 15px;
	background: #333A44;
	// .footer__container
	&__container {
		height: 96px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-family: "Space Mono", monospace;
		@media (max-width: $mobile) {
			flex-direction: column;
			height: auto;
		}
	}

	// .footer__text-wrapper
	&__text-wrapper {
		display: flex;
		@media (max-width: $mobile) {
			margin-top: 32px;
			flex-direction: column;
			align-items: center;
			justify-content: center;
		}
	}

	// .footer__logo
	&__logo {
	}

	// .footer__navigation
	&__navigation {
		margin-left: 58px;
		@media (max-width: $mobile) {
			margin-left: 0;
			margin-top: 20px;
		}
	}

	// .footer__navigation-list
	&__navigation-list {
		@media (max-width: $mobile) {
			flex-direction: column;
			align-items: center;
			row-gap: 8px;
		}
	}

	// .footer__social-icons
	&__social-icons {
		display: flex;
		column-gap: 16px;
		@media (max-width: $mobile) {
			margin-top: 16px;
			margin-bottom: 20px;
		}
	}
}

.social-icons {
	// .social-icons__item
	&__item {
		color: #FCB72B;
		font-size: 24px;
		transition: .3s;

		&:hover {
			color: #E5ECF4;
		}
	}
}
</style>