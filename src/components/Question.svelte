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
			<h3 on:click={toggleExpanded}>{title}</h3>
			<button class="expand_button" on:click={toggleExpanded}>
				{expanded ? '↓' : '→'}
			</button>
		</div>
		{#if expanded}
			<div transition:slide|local class="detail">
				<p>{detail}</p>
			</div>
		{/if}
	</div>
</div>

<style>
	.detail p {
		font-size: 12px;
    line-height: 1.8;
	}
	.detail {
    margin: 20px 40px 20px;
	}
	.title-wrapper h3 {
		font-size: 14px;
		color: #608bc5;
		font-weight: 600;
    cursor: pointer;
	}
	.expand_button {
		width: 35px;
		height: 35px;
		border-radius: 100%;
    color: #608bc5;
		background-color: #ffffff;
    border: 1px solid #608bc5;
	}
	.question-wrapper {
		padding-top: 15px;
		padding-bottom: 15px;
	}
</style>
