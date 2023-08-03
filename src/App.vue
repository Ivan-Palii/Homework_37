<script setup>
import HeaderComponent from "./components/HeaderComponent.vue";
import FooterComponent from "./components/FooterComponent.vue";
import TopicItem from "./components/TopicItem.vue";
import {ref} from "vue";

const topics = ref([{
	title: 'How do I download the app?',
	text: 'To download the Scoot app, you can search “Scoot” in both the App and Google Play stores. An even simpler way to do it would be to click the relevant link at the bottom of this page and you’ll be re-directed to the correct page.',
	active: false,
}, {
	title: 'Can I find a nearby Scoots?',
	text: 'To download the Scoot app, you can search “Scoot” in both the App and Google Play stores. An even simpler way to do it would be to click the relevant link at the bottom of this page and you’ll be re-directed to the correct page.',
	active: false,
}, {
	title: 'Should I wear a helmet?',
	text: 'To download the Scoot app, you can search “Scoot” in both the App and Google Play stores. An even simpler way to do it would be to click the relevant link at the bottom of this page and you’ll be re-directed to the correct page.',
	active: false,
}])

function refreshActive() {
	console.log('Wrapper click')
	topics.value.forEach(item => item.active = false)
}

</script>
<template>
	<div class="wrapper" @click="refreshActive">
		<HeaderComponent/>
		<main class="page">
			<section class="page__faq faq">
				<div class="faq__container">
					<h2 class="faq__title">FAQs</h2>
					<div class="faq__wrapper">
						<h3 class="faq__topic-title">How it works</h3>
						<div class="faq__topic-block topic-block">
							<TopicItem
								v-for="item in topics"
								:topic-item="item"
								:clear-all-topics="refreshActive"
							/>
						</div>
					</div>
				</div>
			</section>
		</main>
		<FooterComponent/>
	</div>
</template>
<style lang="scss">
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
		line-height: 48px; /* 100% */
		letter-spacing: -2.143px;
	}

	// .faq__wrapper
	&__wrapper {
		display: flex;
		column-gap: 30px;
		margin-top: 64px;
	}

	// .faq__topic-title
	&__topic-title {
		color: #495567;
		font-size: 40px;
		font-style: normal;
		font-weight: 700;
		line-height: 48px; /* 120% */
		letter-spacing: -1.786px;
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
		}

		&_active{
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
	}
}

</style>
