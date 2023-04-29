<script setup>
const props = defineProps(['color'])
</script>

<template>
	<div class="square" :class="{ dark: color === 'dark', light: color === 'light' }" />
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
</style>
