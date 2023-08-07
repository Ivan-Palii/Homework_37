<template>
	<div
		@click="itemClick"
		class="topic-block__wrapper"
		:class="{'topic-block__wrapper_active':topicItem.active}"
	>
		<h3
			class="topic-block__title"
			:class="{'topic-block__title_active':topicItem.active}"
		>{{ topicItem.title }}
		</h3>
		<Transition>
			<p
				v-show="topicItem.active"
				class="topic-block__text"
				:class="{'topic-block__text_active':topicItem.active}"
			>{{ topicItem.text }}
			</p>
		</Transition>
	</div>
</template>
<script setup>

const props = defineProps({
	topicItem: {
		type: Object,
		required: true,
	},
	clearAllTopics: {
		type: Function,
		required: true,
	}
})

function itemClick(e) {
	e.stopPropagation()
	const tmp = props.topicItem.active
	props.clearAllTopics()
	props.topicItem.active = !tmp
	console.log('Item click')
}

//topicItem.active = !topicItem.active
</script>
<style scoped>
.v-enter-active,
.v-leave-active {
	transition: 0.5s;
	max-height: 200px;
	margin-top: 24px;
}

.v-enter-from,
.v-leave-to {
	max-height: 0;
	margin-top: 0;
}
</style>