<script setup>
import Square from './Square.vue'

function squareColor(index) {
	const rankIndex = Math.floor(index / 8)
	const fileIndex = index % 8

	if (rankIndex % 2 === fileIndex % 2) {
		return 'light'
	}
	else {
		return 'dark'
	}
}

function coordinate(index) {
	const files = 'abcdefgh'
	const ranks = '87654321'

	return files[index % 8] + ranks[Math.floor(index / 8)]
}
</script>

<template>
	<div class="chessboard">
		<Square
			v-for="(i, index) in Array(64)"
			:color="squareColor(index)"
			:name="coordinate(index)"
		/>
	</div>
</template>

<style scoped>
.chessboard {
	align-self: center;
	aspect-ratio: 1 / 1;
	display: grid;
	grid-template-columns: repeat(8, 1fr);
	margin: 0.5em;
	width: calc(100% - 1em);
	justify-self: center;
}

@media (min-width: 576px) {
	.chessboard {
		max-width: calc(100vh - 1em);
	}
}
</style>
