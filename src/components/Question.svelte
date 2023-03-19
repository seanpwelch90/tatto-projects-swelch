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
		<div class="title-wrapper">
			<button class="expand-title-button" on:click={toggleExpanded}><h2>{title}</h2></button>
			<button class="expand-button" class:expanded on:click={toggleExpanded}>→</button>
		</div>
		{#if expanded}
			<div transition:slide class="detail">
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
		margin: 25px 50px 25px;
	}
	.title-wrapper {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.title-wrapper h2 {
		font-size: 14px;
		color: var(--primary-color);
		font-weight: 600;
		cursor: pointer;
		margin-right: 25px;
	}

	.expand-title-button {
		text-align: left;
		background-color: unset;
		border: none;
	}

	.expand-button {
		width: 35px;
		height: 35px;
		border-radius: 50%;
		color: var(--primary-color);
		background-color: #ffffff;
		border: 1px solid;
		transition: all 0.4s ease;
		display: flex;
		align-items: center;
		justify-content: center;
	}
	.expanded {
		color: #ffffff;
		background-color: var(--primary-color);
		border: 1px solid #ffffff;
		transform: rotateZ(90deg);
	}
	.question-wrapper {
		padding-top: 12px;
		padding-bottom: 12px;
	}

	@media only screen and (max-width: 568px) {
		.title-wrapper h2 {
			margin-left: 25px;
		}

		.expand-button {
			min-width: 35px;
			min-height: 35px;
			border-radius: 50%;
			color: var(--primary-color);
			background-color: #ffffff;
			border: 1px solid;
			transition: all 0.4s ease;
			display: flex;
			align-items: center;
			justify-content: center;
			margin-right: 25px;
		}

		.expanded {
			color: #ffffff;
			background-color: var(--primary-color);
			border: 1px solid #ffffff;
			transform: rotateZ(90deg);
		}
	}
</style>
