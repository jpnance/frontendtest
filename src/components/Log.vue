<script setup>
import { watch } from 'vue'

const props = defineProps(['log'])

watch(
	props.log,
	() => {
		const logElement = document.querySelector('.log')
		logElement.scrollTop = logElement.scrollHeight;
	},
	{
		flush: 'post'
	}
)
</script>
<template>
	<div class="log">
		<div v-for="item in log">{{ item }}</div>
	</div>
</template>

<style scoped>
.log {
	background-color: #333333;
	border-radius: 5px;
	color: white;
	margin: 0.5em;
	overflow-y: scroll;
	padding: 1em;
}
</style>
