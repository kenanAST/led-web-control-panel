<template>
	<div class="outerBound">
		<v-card elevation="24" color="#11131e" shaped tile>
			<div class="grid-container" v-for="led in leds" :key="led.id">
				<v-btn
					class="buttons grid-item"
					v-if="led.enabled"
					v-bind:color="enabledColor"
					@click="toggleButton(led.id)"
				>
					{{ 'Enabled' }}
				</v-btn>
				<v-btn
					class="buttons"
					v-else-if="led.id == 0 || led.id == 7"
					color="#11131e"
					elevation="0"
					@click="toggleButton(led.id)"
				>
				</v-btn>
				<v-btn
					class="buttons grid-item"
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
import io from 'socket.io-client';

export default {
	data: () => ({
		testdata: 'JOSHUA KENAN CINCHES',
		enabledColor: '#1e8d74',
		disabledColor: '#e23058',
		enabledToggle: 'Enabled',
		leds: [],
	}),

	methods: {
		toggleButton(id) {
			this.leds.forEach((led) => {
				led.enabled = false;
			});
			const identifiedLED = this.leds.find((led) => led.id === id);
			identifiedLED.enabled = !identifiedLED.enabled;
			this.socket.emit('toggleLED', identifiedLED.id + 1, this.leds);
		},
	},

	created() {
		this.socket = io('http://192.168.1.8:8000/');
	},

	mounted() {
		this.socket.on('led', (data) => {
			this.leds = data;
		});
	},
};
</script>

<style scoped>
.outerBound {
	margin: auto;
	max-width: 100%;
	padding-top: 25%;
}

.grid-container {
	display: inline-grid;
	grid-template-columns: auto auto auto;
}

.buttons {
	margin: 15px;
	padding: 40px;
	width: 40px;
	max-width: 40px;
	color: white;
}
</style>
