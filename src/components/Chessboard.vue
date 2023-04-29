<script setup>
import Square from './Square.vue'

function squareColor(index) {
	const rankIndex = Math.floor(index / 8)
	const fileIndex = index % 8

	if (rankIndex % 2) {
		if (fileIndex % 2) {
			return 'light'
		}
		else {
			return 'dark'
		}
	}
	else {
		if (fileIndex % 2) {
			return 'dark'
		}
		else {
			return 'light'
		}
	}
}
</script>

<template>
	<div class="chessboard">
		<Square
			v-for="(i, index) in Array(64)"
			:color="squareColor(index)"
		/>
	</div>
</template>

<style scoped>
.chessboard {
	align-self: center;
	aspect-ratio: 1 / 1;
	display: grid;
	grid-template-columns: repeat(8, 1fr);
	max-height: 75vh;
}

@media (min-width: 576px) {
	.chessboard {
		max-height: 100vh;
	}
}
</style>
