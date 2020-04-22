<template>
	<div class="medium ui buttons">
		<button class="ui button" :class="value === 0 ? 'active': ''" @click="input(0)">Unfilled</button>
		<button class="ui button" :class="value === 1 ? 'active': ''" @click="input(1)">Filled</button>
		<button class="ui button" :class="value === 2 ? 'active': ''" @click="input(2)">Highlighted</button>
	</div>
</template>

<script lang="ts">
import { Component, Emit, Prop, Vue } from 'vue-property-decorator';
import 'fomantic-ui-css/components/button.css';

export enum State {
	UNFILLED = 0,
	FILLED = 1,
	HIGHLIGHTED = 2,
}

@Component
export default class ButtonSelector extends Vue {
	@Prop(String) value!: State;

	@Emit()
	input(value: number) { }
}
</script>

<style scoped>
</style>
