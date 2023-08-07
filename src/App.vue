<script setup>
import HeaderComponent from "./components/HeaderComponent.vue";
import BurgerMenuComponent from "./components/BurgerMenuComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";
import {RouterView} from 'vue-router'
import {ref} from "vue";


const showMenuState = ref(false)

function showMenu() {
	showMenuState.value = !showMenuState.value
	console.log(showMenuState.value)
}
</script>
<template>
	<div class="wrapper">
		<HeaderComponent
			:show-menu-state="showMenuState"
			@show-menu="showMenu"
		/>
		<div class="content">
			<Transition>
				<BurgerMenuComponent
					v-if="showMenuState"
					@show-menu="showMenu"
				/>
			</Transition>
			<RouterView/>
			<FooterComponent/>
		</div>
	</div>
</template>
<style lang="scss">
@import "assets/variables.scss";

.navigation-list {
	display: flex;
	column-gap: 32px;
	// .navigation-list__item
	&__item {
		color: #939CAA;
		font-size: 15px;
		font-style: normal;
		font-weight: 700;
		line-height: 25px;
		transition: .3s;

		&:hover {
			color: #FCB72B;
		}
	}
}

.page {
	// .page__faq
	&__faq {

	}
}

.faq {
	font-family: 'Space Mono', monospace;
	// .faq__title
	&__title {
		color: #495567;
		text-align: center;
		font-size: 48px;
		font-style: normal;
		font-weight: 700;

		letter-spacing: -2.143px;
		@media (max-width: $mobile) {
			font-size: 32px;

		}
	}

	// .faq__wrapper
	&__wrapper {
		display: flex;
		column-gap: 30px;
		margin-top: 64px;
		@media (max-width: $tablet) {
			flex-direction: column;
			row-gap: 32px;
		}
		@media (max-width: $mobile) {
			margin-top: 48px;
		}
		@media (max-width: $mobileSmall) {
			margin-top: 24px;
		}
	}

	// .faq__topic-title
	&__topic-title {
		color: #495567;
		font-size: 40px;
		font-style: normal;
		font-weight: 700;
		line-height: 48px; /* 120% */
		letter-spacing: -1.786px;
		@media (max-width: $tablet) {
			align-self: center;
		}
		@media (max-width: $mobile) {
			font-size: 24px;
			line-height: 28px; /* 120% */
			letter-spacing: -1.071px;
		}

	}

	// .faq__topic-block
	&__topic-block {
		flex: 1 0 350px;
	}
}

.topic-block {

	// .topic-block__wrapper
	&__wrapper {
		background: #F2F5F9;
		padding: 32px 40px;
		transition: .3s;
		cursor: pointer;

		&:not(:last-child) {
			margin-bottom: 16px;
		}

		&:hover, &_active {
			background-color: #FFF4DF;
		}

		position: relative;
	}

	// .topic-block__title
	&__title {
		color: #495567;
		font-size: 24px;
		font-style: normal;
		font-weight: 700;
		line-height: 28px; /* 116.667% */
		letter-spacing: -1.071px;

		@media (max-width: $mobile) {
			font-size: 18px;
			line-height: 24px;
			letter-spacing: -0.804px;
			padding-right: 20px;
		}

		&:after {
			content: '';
			display: block;
			width: 14px;
			height: 14px;
			border-style: solid;
			border-width: 0 0 4px 4px;
			border-color: #FCB72B;
			position: absolute;
			top: 32px;
			right: 60px;
			transform: rotate(-45deg);
			transition: .3s;
			@media (max-width: $mobile) {
				right: 30px;
			}
		}

		&_active {
			&:after {
				transform: rotate(135deg);
			}
		}
	}

	// .topic-block__text
	&__text {
		margin-top: 24px;
		color: #495567;
		font-size: 15px;
		font-style: normal;
		font-weight: 400;
		line-height: 25px; /* 166.667% */
		font-family: 'Lexend Deca', sans-serif;
		overflow: hidden;
	}
}

.v-enter-active,
.v-leave-active {
	transition: 0.5s;
}

.v-enter-from,
.v-leave-to {
	opacity: 0;
}
</style>
