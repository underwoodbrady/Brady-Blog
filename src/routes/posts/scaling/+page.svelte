<script lang="ts">
	import ImageButton from '$lib/components/ImageButton.svelte';
	import Arrow from 'virtual:icons/mdi/keyboard-arrow-left';
	import Unliked from 'virtual:icons/mdi/like-outline';
	import Liked from 'virtual:icons/mdi/like';

	let liked: boolean = false;
    let likeButtonText = ['Like','Liked'];
</script>

<article>
	<a href="/" class="flex items-center space-x-1 text-light mb-6 underline"
		><Arrow width={16} height={16} />Back to blog</a
	>

	<div class="mb-6 flex items-center justify-between">
		<h4>Scaling Laws Applied At Scale</h4>
		<p class="text-secondary">June 6th 2024</p>
	</div>

	<div class="space-y-4 mb-12">
		<p class="text-preview leading-7">
			There are two things from our announcement today I wanted to highlight. First, a key part of
			our mission is to put very capable AI tools in the hands of people for free (or at a great
			price). I am very proud that we’ve made the best model in the world available for free in
			ChatGPT, without ads or anything like that.
		</p>
		<p class="text-preview leading-7">
			Our initial conception when we started OpenAI was that we’d create AI and use it to create all
			sorts of benefits for the world. Instead, it now looks like we’ll create AI and then other
			people will use it to create all sorts of amazing things that we all benefit from.
		</p>
		<p class="text-preview leading-7">
			We are a business and will find plenty of things to charge for, and that will help us provide
			free, outstanding AI service to (hopefully) billions of people. Second, the new voice (and
			video) mode is the best computer interface I’ve ever used. It feels like AI from the movies;
			and it’s still a bit surprising to me that it’s real.
		</p>
		<p class="text-preview leading-7">
			Getting to human-level response times and expressiveness turns out to be a big change. The
			original ChatGPT showed a hint of what was possible with language interfaces; this new thing
			feels viscerally different. It is fast, smart, fun, natural, and helpful. Talking to a
			computer has never felt really natural for me; now it does. As we add (optional)
			personalization, access to your information, the ability to take actions on your behalf, and
			more, I can really see an exciting future where we are able to use computers to do much more
			than ever before. Finally, huge thanks to the team that poured so much work into making this
			happen!
		</p>
	</div>
	<div class="flex items-center space-x-2">
		<ImageButton title={likeButtonText[+liked]} onClick={()=>
            {
                liked = !liked;
            }}>
			{#if liked}
				<Liked />
			{:else}
				<Unliked />
			{/if}
		</ImageButton>
        <p class="text-sm text-secondary">{3+(+liked)}</p>
	</div>
</article>
