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

<div class="mr-20 flex-1">
	<ArticlePreview
		title="Scaling Laws Applied at Scale"
		introduction="What can we learn from pushing scaling laws to their limits"
		dim={mousedOver != 1 && mousedOver != 0}
		onMouseOver={() => dimArticles(1)}
		onMouseLeave={removeDim}
		likes={2}
		link="scaling"
	/>
	<ArticlePreview
		title="A Case For Open Training Data"
		introduction="Why we shouldn't worry so much about what data AI is training on"
		dim={mousedOver != 2 && mousedOver != 0}
		onMouseOver={() => dimArticles(2)}
		onMouseLeave={removeDim}
		likes={5}
	/>
	<ArticlePreview
		title="React Native vs. Flutter"
		introduction="In depth guide for when to use what framework"
		dim={mousedOver != 3 && mousedOver != 0}
		onMouseOver={() => dimArticles(3)}
		onMouseLeave={removeDim}
		likes={2}
	/>
	<ArticlePreview
		title="Welcome to my Blog"
		introduction="An introductory post to my blog which will cover tech news and other things"
		dim={mousedOver != 4 && mousedOver != 0}
		onMouseOver={() => dimArticles(4)}
		onMouseLeave={removeDim}
	/>
	<p
		class="text-sm text-neutral-100 opacity-70 hover:opacity-100 duration-150 transition-opacity text-center mt-8 cursor-pointer"
	>
		Show More
	</p>
</div>

<section class="w-8">
	<Timeline />
</section>
