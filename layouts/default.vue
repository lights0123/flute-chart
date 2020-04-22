<template>
	<div>
		<div class="wrapper">
			<nuxt />
			<footer class="ui inverted vertical footer segment hide-print">
				<div class="ui container">
					<div class="ui stackable inverted divided equal height stackable grid">
						<div class="three wide column">
							<h4 class="ui inverted header">Ben Schattinger</h4>
							<div class="ui inverted link list">
								<a href="https://lights0123.com" class="item"><i class="globe icon" /> My Website</a>
								<a href="https://github.com/lights0123" class="item">
									<i class="github icon" />
									My GitHub
								</a>
							</div>
						</div>
						<div class="three wide column">
							<h4 class="ui inverted header">Copyright</h4>
							<div class="ui inverted link list">
								<nuxt-link to="/license" class="item">
									<i class="copyright outline icon" />
									Copyright 2020 Ben Schattinger under the MPL 2.0 License.
								</nuxt-link>
								<a href="https://github.com/lights0123/flute-chart" class="item">
									<i class="icon github" />
									This project is open source! Fork this on GitHub
								</a>
							</div>
						</div>
						<div class="seven wide column">
							<h4 class="ui inverted header">About</h4>
							<p>
								This is a website for easily creating great-looking flute fingering charts. It supports
								any fingering, with special support for highlighting trill keys.
							</p>
						</div>
					</div>
				</div>
			</footer>
		</div>
	</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import 'fomantic-ui-css/components/segment.css';
import 'fomantic-ui-css/components/container.css';
import 'fomantic-ui-css/components/grid.css';
import 'fomantic-ui-css/components/icon.css';
import 'fomantic-ui-css/components/header.css';
import 'fomantic-ui-css/components/list.css';

@Component
export default class Default extends Vue {
}
</script>

<style lang="scss">
.wrapper {
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	min-height: 100vh;
}

.footer {
	margin-top: 2rem;
}

@media print {
	.hide-print {
		display: none;
	}
}
</style>
