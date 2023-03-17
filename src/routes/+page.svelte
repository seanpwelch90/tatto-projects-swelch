<script>
	import Question from '../components/Question.svelte';
</script>

<div class="page-wrapper">
	<div class="question-wrapper">
		<Question
			class="question"
			title="Who is Joe Mallory"
			detail="Probably best described as a humble and light-spirited digital Chimera, theres no industry buzz-word label that fits Joe. And thats just fine with him."
		/>
		<Question
			class="question"
			title="Who is Joe Mallory"
			detail="Probably best described as a humble and light-spirited digital Chimera, theres no industry buzz-word label that fits Joe. And thats just fine with him."
		/>
		<Question
			class="question"
			title="Who is Joe Mallory"
			detail="Probably best described as a humble and light-spirited digital Chimera, theres no industry buzz-word label that fits Joe. And thats just fine with him."
		/>
	</div>
</div>

<style>
	:global(body) {
		background: linear-gradient(to bottom, #ffffff 50%, #f6f8fc 50%);
	}
	:global(*) {
		margin: 0;
		padding: 0;
	}
	.question-wrapper {
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		padding-left: 40px;
		padding-right: 40px;
		max-width: 80vw;
		box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
		border-radius: 20px;
		background-color: #ffffff;
		margin: 45px auto auto;
	}

	.question-wrapper :global(.question:not(:last-child)) {
		border-bottom: 1px solid #608bc5;
	}
	.page-wrapper {
		min-height: 100vh;
	}
</style>
