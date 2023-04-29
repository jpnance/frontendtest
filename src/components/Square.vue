<script setup>
import { ref } from 'vue'

const props = defineProps(['color', 'name'])

const highlighted = ref(false)

function toggleHighlight() {
	highlighted.value = !highlighted.value
}
</script>

<template>
	<div
		class="square"
		:class="{ dark: color === 'dark', light: color === 'light', highlighted: highlighted }"
		@click="toggleHighlight"
	/>
</template>

<style scoped>
.square {
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
