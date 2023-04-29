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
	max-height: calc(75vh - 1em);
	margin: 0.5em;
}

@media (min-width: 576px) {
	.chessboard {
		max-height: calc(100vh - 1em);
	}
}
</style>
