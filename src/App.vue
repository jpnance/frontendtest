<script setup>
import Chessboard from './components/Chessboard.vue'
import Log from './components/Log.vue'
</script>

<template>
  <main>
    <Chessboard />
	<Log />
  </main>
</template>

<style scoped>
main {
	display: grid;
	grid-template-rows: 75vh 25vh;
	height: 100vh;
}

@media (min-width: 576px) {
	main {
		grid-template-columns: auto 250px;
		grid-template-rows: none;
	}
}
</style>
