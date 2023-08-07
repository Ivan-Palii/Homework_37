<script setup>
import {ref} from "vue";
import TopicItem from "../components/TopicItem.vue";

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
	topics.value.forEach(item => item.active = false)
}
</script>
<template>
	<main class="page" @click="refreshActive">
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
</template>
<style scoped>
</style>