<script>
	import Question from '../components/Question.svelte';
  let questionCount = 7
</script>

<div class="page-wrapper">
	<div class="question-wrapper">
		{#each Array(questionCount) as _, i}
			<Question
				class="question"
				title="Lorem psum Dolor Sit Amet, Consectetur Adipiscing Elst"
				detail="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas velit urna, placerat vitae est vel, sodales tristique metus. Suspendisse molestie nulla purus, nec placerat est pulvinar eget. Pellentesque lobortis ante luctus risus tincidunt aliquet. Duis in nibh tellus. Proin dignissim enim quis libero efficitur lacinia."
			/>
		{/each}
	</div>
</div>

<style>
	:global(*) {
		margin: 0;
		padding: 0;
	}
	:global(:root) {
		--primary-color: #608bc5;
	}
	:global(body) {
		background: linear-gradient(to bottom, #ffffff 50%, #f6f8fc 50%);
	}
	.question-wrapper {
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
			Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
		padding-left: 40px;
		padding-right: 40px;
		max-width: 80vw;
		box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
		border-radius: 20px;
		background-color: #ffffff;
		margin: 45px auto auto;
	}

	.question-wrapper :global(.question:not(:last-child)) {
		border-bottom: 1px solid var(--primary-color);
	}
	.page-wrapper {
		min-height: 100vh;
	}
</style>
