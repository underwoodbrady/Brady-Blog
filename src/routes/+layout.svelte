<script lang="ts">
	import '../app.css';
	import ImageButton from '$lib/components/ImageButton.svelte';
	import SearchInput from '$lib/components/SearchInput.svelte';
	import Gmail from 'virtual:icons/mdi/gmail';
	import EmailPlus from 'virtual:icons/mdi/cursor-default-click';
	import Insta from 'virtual:icons/mdi/instagram';
	import Logo from 'virtual:icons/mdi/pencil-ruler';

	let highlightEl: HTMLDivElement;

	let showEmailInput: boolean = false;

	function handleMousemove(e: MouseEvent) {
		highlightEl.style.left = `${e.clientX}px`;
		highlightEl.style.top = `${e.clientY}px`;
	}
</script>

<svelte:window on:mousemove={handleMousemove} />
<div class="bg-background min-h-screen">
	<div class="p-8 lg:p-16 max-w-screen-xl mx-auto">
		<div
			class="fixed w-[800px] h-[800px] rounded-full bg-radient-ellipse-c from-primary/50 from-0% to-background to-70% -translate-x-1/2 -translate-y-1/2"
			bind:this={highlightEl}
		></div>
		<div class="z-10 fixed top-0 left-0 w-screen h-screen bg-background/60"></div>
		<main class="z-20 relative flex flex-col lg:flex-row w-full">
			<section class="w-[278px] h-[400px] relative">
				<header class="mb-8">
					<div class="flex items-center space-x-4 mb-3">
						<h1>Brady's Blog</h1>
						<Logo width={44} height={44} class="text-secondary" />
					</div>
					<h2>good ideas on occasion</h2>
				</header>

				<div class="space-y-4">
					{#if showEmailInput}
						<p class="text-sm text-preview leading-6">
							Enter your email address to get informed about new posts. Unsubscribe anytime.
						</p>
						<input
							class="w-full text-sm border-light/20 border-2 bg-light/10 rounded-md px-2 py-1 outline-none placeholder:text-neutral-400 text-neutral-100"
							placeholder="Email Address"
						/>
						<ImageButton
							title="Subscribe"
							onClick={() => {
								showEmailInput = false;
							}}
						></ImageButton>
					{:else}
						<ImageButton
							title="Subscribe by Email"
							onClick={() => {
								showEmailInput = true;
							}}
						>
							<Gmail />
						</ImageButton>
						<a href="https://www.instagram.com/dev.brady/" target="_blank" class="block">
							<ImageButton title="Follow @dev.brady">
								<Insta />
							</ImageButton>
						</a>
					{/if}
				</div>

				<footer class="absolute bottom-0 w-full mt-12 mb-8 lg:mb-0">
					<SearchInput placeholder="Search posts" />
				</footer>
			</section>

			<section class="flex-1 lg:ml-24 flex">
				<slot />
			</section>
		</main>
	</div>
</div>
