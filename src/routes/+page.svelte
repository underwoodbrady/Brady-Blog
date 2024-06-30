<script lang="ts">
	import ArticlePreview from '$lib/components/ArticlePreview.svelte';
    import Timeline from '$lib/components/Timeline.svelte';

	let mousedOver = 0;

	function dimArticles(x: number) {
		mousedOver = x;
	}

	function removeDim() {
		mousedOver = 0;
	}
</script>

<div class="mr-20">
	<ArticlePreview
		title="Scaling Laws Applied at Scale"
		introduction="What can we learn from pushing scaling laws to their limits"
		dim={mousedOver != 1 && mousedOver != 0}
		onMouseOver={() => dimArticles(1)}
		onMouseLeave={removeDim}
	/>
	<ArticlePreview
		title="A Case For Open Training Data"
		introduction="Why we shouldn't worry so much about what data AI is training on"
		dim={mousedOver != 2 && mousedOver != 0}
		onMouseOver={() => dimArticles(2)}
		onMouseLeave={removeDim}
	/>
	<ArticlePreview
		title="React Native vs. Flutter"
		introduction="In depth guide for when to use what framework"
		dim={mousedOver != 3 && mousedOver != 0}
		onMouseOver={() => dimArticles(3)}
		onMouseLeave={removeDim}
	/>
	<ArticlePreview
		title="Welcome to my Blog"
		introduction="An introductory post to my blog which will cover tech news and other things"
		dim={mousedOver != 4 && mousedOver != 0}
		onMouseOver={() => dimArticles(4)}
		onMouseLeave={removeDim}
	/>
</div>

<section class="w-4">
	<Timeline />
</section>
