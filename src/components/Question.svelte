<script>
	let expanded = false;
	export let title;
	export let detail;

	function toggleExpanded() {
		expanded = !expanded;
	}
</script>

<div class="title" on:click={toggleExpanded}>
	<h3>{title}</h3>
	{#if detail}
		<div class="detail">
			<p>{detail}</p>
		</div>
	{/if}
</div>

<style>
</style>
