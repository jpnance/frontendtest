<script setup>
import { ref, inject } from 'vue'

const props = defineProps(['color', 'name'])

const log = inject('log')
const highlighted = ref(false)

function toggleHighlightAndLogEvent(name) {
	highlighted.value = !highlighted.value

	if (highlighted.value) {
		log.addToLog(`${name} was highlighted`)
	}
	else {
		log.addToLog(`${name} was unhighlighted`)
	}
}
</script>

<template>
	<div
		class="square"
		:class="{ [color]: true, highlighted: highlighted }"
		@click="toggleHighlightAndLogEvent(name)"
	/>
</template>

<style scoped>
.square {
	cursor: pointer;
}

.square.light {
	background-color: bisque;
}

.square.dark {
	background-color: burlywood;
}

.square.light.highlighted {
	background-color: pink;
}

.square.dark.highlighted {
	background-color: lightpink;
}
</style>
