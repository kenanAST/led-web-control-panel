<template>
	<control-panel />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import ControlPanel from './components/ControlPanel.vue';

export default {
	name: 'App',

	components: {
		HelloWorld,
		ControlPanel,
	},

	data: () => ({
		again: 'TOPPPP HELLO WORLD',
	}),
};
</script>

<style>
body {
	background-color: #0f1219;
}
</style>
