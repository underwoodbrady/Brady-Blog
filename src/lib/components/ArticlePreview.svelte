<script lang="ts">
	export let title: string;
	export let introduction: string;
	import Arrow from 'virtual:icons/mdi/arrow-top-right';
	import Liked from 'virtual:icons/mdi/like';
	export let likes: number = 0;
	export let dim: boolean = false;
	export let link: string = "/"
	export let onMouseOver: () => void;
	export let onMouseLeave: () => void;
</script>

<a href={`/posts/${link}`}>
<article
	class={'mb-4 hover:bg-white/10 p-4 rounded-md cursor-pointer group duration-150' +
		(dim ? ' opacity-70' : ' opacity-100')}
	on:mouseover={onMouseOver}
	on:focus={onMouseOver}
	on:mouseleave={onMouseLeave}
>
	<div class="flex items-center justify-between">
		<div class="flex items-center space-x-2 mb-2">
			<h3 class="">{title}</h3>
			<Arrow class="text-light" />
		</div>
		{#if likes}
			<div class="flex items-center space-x-1 text-preview group-hover:text-neutral-300 text-xs">
				<Liked  />
				<p>{likes}</p>
			</div>
		{/if}
	</div>

	<p class="text-preview group-hover:text-neutral-300 overflow-hidden whitespace-nowrap">
		{introduction}
	</p>
</article>
</a>