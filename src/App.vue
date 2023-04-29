<script setup>
import { ref, provide } from 'vue'
import Chessboard from './components/Chessboard.vue'
import Log from './components/Log.vue'

const log = ref([])

function addToLog(item) {
	log.value.push(item)
}

provide('log', {
	log,
	addToLog
})
</script>

<template>
  <main>
    <Chessboard />
	<Log :log="log" />
  </main>
</template>

<style scoped>
main {
	background-color: black;
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
