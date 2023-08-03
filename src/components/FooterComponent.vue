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
.footer {
	background: #333A44;
	// .footer__container
	&__container {
		height: 96px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-family: "Space Mono", monospace;
	}

	// .footer__text-wrapper
	&__text-wrapper {
		display: flex;
	}

	// .footer__logo
	&__logo {
	}

	// .footer__navigation
	&__navigation {
		margin-left: 58px;
	}

	// .footer__navigation-list
	&__navigation-list {
	}

	// .footer__social-icons
	&__social-icons {
		display: flex;
		column-gap: 16px;
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