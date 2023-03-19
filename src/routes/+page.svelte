<script>
	import Question from '../components/Question.svelte';
	let questionArray = Array(7)
		.fill(null)
		.map(() => ({
			question: 'Lorem psum Dolor Sit Amet, Consectetur Adipiscing Elst?',
			answer:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas velit urna, placerat vitae est vel, sodales tristique metus. Suspendisse molestie nulla purus, nec placerat est pulvinar eget. Pellentesque lobortis ante luctus risus tincidunt aliquet. Duis in nibh tellus. Proin dignissim enim quis libero efficitur lacinia.'
		}));
</script>

<div class="page-wrapper">
	<main class="content">
		<section class="questions-wrapper">
			{#each questionArray as question}
				<Question class="question" title={question.question} detail={question.answer} />
			{/each}
		</section>
	</main>
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
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu,
			Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
	}

	.page-wrapper {
		background: linear-gradient(to bottom, #ffffff 50%, #f6f8fc 50%);
	}

	.content {
		height: 100vh;
		width: 100vw;
		overflow: auto;
	}

	.questions-wrapper :global(.question:not(:last-child)) {
		border-bottom: 1px solid var(--primary-color);
	}

	@media only screen and (max-width: 568px) {
		.questions-wrapper {
			background-color: #ffffff;
		}
	}

	@media only screen and (min-width: 569px) and (max-width: 768px) {
		.questions-wrapper {
			padding: 12px 25px 12px 25px;
			max-width: 80vw;
			box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
			border-radius: 10px;
			background-color: #ffffff;
			margin: 25px auto auto;
		}
	}

	@media only screen and (min-width: 769px) {
		.questions-wrapper {
			padding: 25px 50px 25px 75px;
			max-width: 80vw;
			box-shadow: 0 3px 10px rgb(0 0 0 / 0.2);
			border-radius: 10px;
			background-color: #ffffff;
			margin: 50px auto auto;
		}
	}
</style>
