<template>
	<main>
		<div class="ui text container">
			<div class="ui stackable two column grid">
				<div v-for="val in keys" :key="val.name" class="column">
					<field-label>{{ val.name }}</field-label>
					<button-selector v-model="val.state" />
				</div>
			</div>
			<img :src="svgData" class="model">
		</div>
	</main>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import 'fomantic-ui-css/components/container.css';
import 'fomantic-ui-css/components/grid.css';
import FieldLabel from '../components/FieldLabel.vue';
import ButtonSelector, { State } from '../components/ButtonSelector.vue';

const REGEX_DOUBLE_QUOTE = /"/g;
const REGEX_MULTIPLE_SPACES = /\s+/g;
const REGEX_UNSAFE_CHARS = /[{}|\\^~[\]`"<>#%]/g;

const stateColorMapping = {
	[State.UNFILLED]: 'fill: none;',
	[State.FILLED]: 'fill: #121212;',
	[State.HIGHLIGHTED]: 'fill: red;',
};

@Component({
	components: {
		FieldLabel,
		ButtonSelector,
	},
})
export default class Index extends Vue {
	private keys = {
		'b-flat': { name: 'B Flat', state: 0 },
		'b-natural': { name: 'B Natural', state: 0 },
		'lh-1': { name: 'Left Hand 1', state: 0 },
		'lh-2': { name: 'Left Hand 2', state: 0 },
		'lh-3': { name: 'Left Hand 3', state: 0 },
		'g-sharp': { name: 'G Sharp', state: 0 },
		'rh-1': { name: 'Right Hand 1', state: 0 },
		'rh-2': { name: 'Right Hand 2', state: 0 },
		'rh-3': { name: 'Right Hand 3', state: 0 },
		'rh-4': { name: 'Right Hand 4', state: 0 },
		'tr-1': { name: 'Trill 1', state: 0 },
		'tr-2': { name: 'Trill 2', state: 0 },
	};

	private get svg(): string {
		const styles = Object.entries(this.keys).map(([key, { state }]) => {
			return `#${key} {${stateColorMapping[state]}}`;
		}).join('');
		return `<svg
	xmlns="http://www.w3.org/2000/svg"
	height="20.537807"
	width="66.389465"
	version="1.1"
>
	<defs>
		<style lang="text/css">
		path {
			stroke: #121212;
			stroke-width: 0.361;
			stroke-linecap: butt;
			stroke-linejoin: miter;
			stroke-miterlimit: 4;
			stroke-dasharray: none;
			stroke-opacity: 1;
		}
		.divider {
			stroke-width: 0.65;
		}
		${styles}
		</style>
	</defs>
	<g transform="matrix(1.3333333,0,0,-1.3333333,-645.86465,198.99194)">
		<path
			id="b-flat"
			d="m 488.876,135.8621 c 0,1.02 -0.824,1.841 -1.842,1.841 -1.018,0 -1.842,-0.821 -1.842,-1.841 0,-1.011 0.824,-1.841 1.842,-1.841 1.018,0 1.842,0.83 1.842,1.841 z"
		/>
		<path
			id="b-natural"
			d="m 496.6721,137.7036 c 0.313,-0.019 0.257,-0.425 0,-0.479 -0.618,-0.189 -2.168,-0.64 -2.862,-1.534 -0.66,-0.821 -1.422,-1.616 -2.409,-1.561 -1.045,0.053 -1.503,0.766 -1.391,2.004 0.125,1.362 1.391,1.57 1.391,1.57 z"
		/>
		<path
			id="lh-1"
			d="m 489.49,142.3131 c 0,1.354 -1.1,2.455 -2.456,2.455 -1.356,0 -2.455,-1.101 -2.455,-2.455 0,-1.354 1.099,-2.455 2.455,-2.455 1.356,0 2.456,1.101 2.456,2.455 z"
		/>
		<path
			id="lh-2"
			d="m 496.637,142.3131 c 0,1.354 -1.099,2.455 -2.456,2.455 -1.356,0 -2.454,-1.101 -2.454,-2.455 0,-1.354 1.098,-2.455 2.454,-2.455 1.357,0 2.456,1.101 2.456,2.455 z"
		/>
		<path
			id="lh-3"
			d="m 503.785,142.3131 c 0,1.354 -1.1,2.455 -2.457,2.455 -1.355,0 -2.455,-1.101 -2.455,-2.455 0,-1.354 1.1,-2.455 2.455,-2.455 1.357,0 2.457,1.101 2.457,2.455 z"
		/>
		<path
			id="g-sharp"
			d="m 505.77449,147.17993 c -0.127,0.471 -0.16896,0.52739 -0.29,0.759 -0.35331,0.56766 -1.133,1.047 -2.079,1.119 -0.895,0.063 -2.451,-0.461 -1.621,-1.426 0.662,-0.776 2.335,-0.559 2.834,-0.947 0.65,-0.506 0.364,-3.061 0.396,-3.421 0.047,-0.542 0.806,-0.47 0.76,0.063 z"
		/>
		<path class="divider"
			d="m 507.3439,139.1001 v 6.57"
		/>
		<path
			id="rh-1"
			d="m 514.1799,142.313 c 0,1.354 -1.099,2.455 -2.456,2.455 -1.355,0 -2.456,-1.101 -2.456,-2.455 0,-1.354 1.101,-2.455 2.456,-2.455 1.357,0 2.456,1.101 2.456,2.455 z"
		/>
		<path
			id="rh-2"
			d="m 522.0034,142.313 c 0,1.354 -1.099,2.455 -2.455,2.455 -1.357,0 -2.457,-1.101 -2.457,-2.455 0,-1.354 1.1,-2.455 2.457,-2.455 1.356,0 2.455,1.101 2.455,2.455 z"
		/>
		<path
			id="rh-3"
			d="m 529.8269,142.313 c 0,1.354 -1.098,2.455 -2.454,2.455 -1.357,0 -2.456,-1.101 -2.456,-2.455 0,-1.354 1.099,-2.455 2.456,-2.455 1.356,0 2.454,1.101 2.454,2.455 z"
		/>
		<path
			id="rh-4"
			d="m 532.9731,141.1406 c 0,0.613 1.037,0.613 1.037,0 0,-0.317 -0.005,-2.149 0,-4.756 0.001,-0.534 -0.361,-0.668 -0.765,-0.713 -0.901,-0.091 -2.45,0.901 -2.521,2.345 -0.081,1.617 1.499,2.113 1.888,2.265 0.465,0.173 0.361,0.443 0.361,0.859 z"
		/>
		<path
			id="tr-1"
			d="m 516.41265,140.15106 c 0,1.038 -0.514,1.155 -0.776,1.155 -0.265,0 -0.778,-0.117 -0.778,-1.155 v -1.877 c 0,-1.038 0.513,-1.154 0.778,-1.154 0.262,0 0.776,0.116 0.776,1.154 z"
		/>
		<path
			id="tr-2"
			d="m 524.23615,140.15106 c 0,1.038 -0.514,1.155 -0.776,1.155 -0.265,0 -0.778,-0.117 -0.778,-1.155 v -1.877 c 0,-1.038 0.513,-1.154 0.778,-1.154 0.262,0 0.776,0.116 0.776,1.154 z"
		/>
	</g>
</svg>`;
	}

	private get svgData(): string {
		const data = this.svg
			.replace(REGEX_DOUBLE_QUOTE, '\'')
			.replace(REGEX_MULTIPLE_SPACES, ' ')
			.replace(REGEX_UNSAFE_CHARS, match => `%${match[0].charCodeAt(0).toString(16).toUpperCase()}`)
			.trim();

		return `data:image/svg+xml,${data}`;
	}
}
</script>

<style scoped lang="scss">
.grid {
	margin-left: -0.2rem;
	margin-right: -0.2rem;
}

.model {
	margin-top: 2rem;
	width: 100%;
}
</style>
