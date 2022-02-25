<template>
	<div>
		<v-card elevation="24" color="#11131e" shaped tile>
			<v-btn class="buttons" color="#1e8d74"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#00897B"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
			<v-btn class="buttons" color="#e23058"> {{ enabledToggle }} </v-btn>
		</v-card>
	</div>
</template>

<script>
export default {
	data: () => ({
		testdata: 'JOSHUA KENAN CINCHES',
		enabledColor: '#e23058',
		enabledToggle: 'Enabled',
	}),
};
</script>

<style scoped>
div {
	margin: auto;
	max-width: 60%;
	padding: 5%;
}

.buttons {
	margin: 20px;
	color: white;
}
</style>
