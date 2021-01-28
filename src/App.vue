<template>
	<div id="app">
		<div class="matrix">
			<div class="axis axis-left"></div>
			<div class="axis axis-top">Urgent</div>
			<div class="axis axis-top">Not Urgent</div>

			<div class="axis axis-left imp">Important</div>
			<div class="square imp-urg"><div class="content">
				<div class="info">
					<h3>Do it!</h3>
					<p>Things w/clear deadlines, and consequences for not taking immediate action.</p>
				</div>
			</div></div>
			<div class="square imp-not-urg"><div class="content">
				<div class="info">
					<h3>Schedule it!</h3>
					<p>Activities without a set deadline. Easy to procrastinate on.</p>
				</div>
			</div></div>

			<div class="axis axis-left">Not important</div>
			<div class="square not-imp-urg"><div class="content">
				<div class="info">
					<h3>Delegate it!</h3>
					<p>Things that need to be done, boring busy work.</p>
				</div>
			</div></div>
			<div class="square not-imp-not-urg"><div class="content">
				<div class="info">
					<h3>Delete it!</h3>
					<p>Distractions that make you feel worse afterward. Can be ok but in moderation.</p>
				</div>
			</div></div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'App',
		components: {},
	}
</script>

<style>
	:root {
		--bgc: #eee;

		--axis-left-width: 5%;
		--axis-padding: .5rem;
		--axis-top-width: calc((100% - var(--axis-left-width))/2 - var(--axis-padding) - var(--square-border-width));

		--square-border-width: 1px;
		--square-border-color: #666;
		--square-width: calc((100% - var(--axis-left-width))/2 - 2*var(--square-border-width) - var(--axis-padding));

		--imp-urg-bgc: #fadbd7;
		--imp-not-urg-bgc: #e8f8da;
		--not-imp-urg-bgc: #fdecd1;
		--not-imp-not-urg-bgc: #fff9e5;

		--content-padding: 2rem;
		--content-width: calc(100% - 2*var(--content-padding));
	}
	* {
		padding: 0;
		margin: 0;
	}
	body {
		margin: 0;
		font-family: Arial, sans-serif;
	}
	#app {
		height: 100vh;
		background-color: var(--bgc);

		display: flex;
		justify-content: center;
		align-items: center;
	}

	.matrix {
		display: flex;
		flex-wrap: wrap;

		width: 80%;
	}

	.axis {
		font-size: 1.1rem;
	}
	.axis-top {
		display: flex;
		justify-content: center;

		padding-bottom: var(--axis-padding);

		width: var(--axis-top-width)
	}
	.axis-left {
		display: flex;
		justify-content: center;
		align-items: flex-end;

		width: var(--axis-left-width);
		padding-left: var(--axis-padding);

		writing-mode: vertical-rl;
		text-orientation: mixed;

		transform: rotate(180deg);
	}

	.square {
		position: relative;

		width: var(--square-width);
		border: var(--square-border-width) solid var(--square-border-color);
	}
	.square:after {
		content: '';
		display: block;
		padding-top: 100%;
	}
	.content {
		position: absolute;
		width: var(--content-width);
		height: var(--content-width);

		padding: var(--content-padding);
	}

	.imp-urg {
		background-color: var(--imp-urg-bgc);
	}
	.imp-not-urg {
		background-color: var(--imp-not-urg-bgc);
	}
	.not-imp-urg {
		background-color: var(--not-imp-urg-bgc);
	}
	.not-imp-not-urg {
		background-color: var(--not-imp-not-urg-bgc);
	}
</style>
