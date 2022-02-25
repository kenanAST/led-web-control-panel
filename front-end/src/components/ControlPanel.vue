<template>
	<div class="outerBound">
		<v-card elevation="24" color="#11131e" shaped tile>
			<div v-for="led in leds" :key="led.id">
				<v-btn
					class="buttons"
					v-if="led.enabled"
					v-bind:color="enabledColor"
					@click="toggleButton(led.id)"
				>
					{{ 'Enabled' }}
				</v-btn>
				<v-btn
					class="buttons"
					v-else
					v-bind:color="disabledColor"
					@click="toggleButton(led.id)"
				>
					{{ 'Disabled' }}
				</v-btn>
			</div>

			<!-- <v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" v-bind:color="enabledColor">
				{{ enabledToggle }}
			</v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn> -->
		</v-card>
	</div>
</template>

<script>
export default {
	data: () => ({
		testdata: 'JOSHUA KENAN CINCHES',
		enabledColor: '#1e8d74',
		disabledColor: '#e23058',
		enabledToggle: 'Enabled',
		leds: [
			{ id: 0, enabled: true },
			{ id: 1, enabled: false },
			{ id: 2, enabled: true },
			{ id: 3, enabled: true },
			{ id: 4, enabled: true },
			{ id: 5, enabled: true },
			{ id: 6, enabled: true },
			{ id: 7, enabled: true },
			{ id: 8, enabled: true },
		],
	}),

	methods: {
		toggleButton(id) {
			const identifiedLED = this.leds.find((led) => led.id === id);
			identifiedLED.enabled = !identifiedLED.enabled;
		},
	},
};
</script>

<style scoped>
.outerBound {
	margin: auto;
	max-width: 60%;
	padding: 5%;
}

.buttons {
	margin: 20px;
	padding: 20px;
	max-width: 10%;
	color: white;
}
</style>
