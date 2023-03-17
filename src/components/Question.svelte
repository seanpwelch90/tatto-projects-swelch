<script>
	import { slide } from 'svelte/transition';

	export let title = '';
	export let detail = '';
	let expanded = false;

	function toggleExpanded() {
		expanded = !expanded;
	}
</script>

<div class={$$props.class}>
	<div class="question-wrapper">
		<div
			class="title-wrapper"
			style="display: flex; justify-content: space-between; align-items: baseline"
		>
			<!-- svelte-ignore a11y-click-events-have-key-events -->
			<h3 on:click={toggleExpanded}>{title}</h3>
			<button class="expand_button" class:expanded on:click={toggleExpanded}>→</button>
		</div>
		{#if expanded}
			<div transition:slide|local class="detail">
				<p>{detail}</p>
			</div>
		{/if}
	</div>
</div>

<style>
	:global(:root) {
		--primary-color: #608bc5;
	}
	.detail p {
		font-size: 12px;
		line-height: 1.8;
	}
	.detail {
		margin: 20px 40px 20px;
	}
	.title-wrapper h3 {
		font-size: 14px;
		color: var(--primary-color);
		font-weight: 600;
		cursor: pointer;
	}
	.expand_button {
		width: 35px;
		height: 35px;
		border-radius: 100%;
		color: var(--primary-color);
		background-color: #ffffff;
		border: 1px solid;
		transition: all 0.4s ease;
	}
	.expanded {
		color: #ffffff;
		background-color: var(--primary-color);
		border: 1px solid #ffffff;
		transform: rotateZ(90deg);
	}
	.question-wrapper {
		padding-top: 15px;
		padding-bottom: 15px;
	}
</style>
