<script lang="ts">
	import ArticlePreview from '$lib/components/ArticlePreview.svelte';
import Button from '$lib/components/ImageButton.svelte';
	import SearchInput from '$lib/components/SearchInput.svelte';
	import Timeline from '$lib/components/Timeline.svelte';
	import Gmail from 'virtual:icons/mdi/gmail';
	import Insta from 'virtual:icons/mdi/instagram';
	import Logo from 'virtual:icons/mdi/pencil-ruler';

    let mousedOver = 0;
    
    function dimArticles(x:number){
        mousedOver= x;
    }

    function removeDim(){
        mousedOver= 0;
    }
</script>

<section class="">
	<header class="mb-8">
		<div class="flex items-center space-x-4 mb-3">
			<h1>Brady's Blog</h1>
			<Logo width={44} height={44} class="text-secondary" />
		</div>
		<h2>good ideas on occasion</h2>
	</header>

	<div class="space-y-4">
		<Button title="Subscribe by Email">
			<Gmail />
		</Button>

		<Button title="Follow @dev.brady">
			<Insta />
		</Button>
	</div>

	<footer class="mt-[70%]">
		<SearchInput placeholder="Search posts" />
	</footer>
</section>

<section class="flex-1 ml-24 mr-16">
    <div>
        <ArticlePreview title="Scaling Laws Applied at Scale" introduction="What can we learn from pushing scaling laws to their limits" dim = {mousedOver != 1 && mousedOver !=0} onMouseOver={()=>dimArticles(1)}  onMouseLeave={removeDim}/>
        <ArticlePreview title="A Case For Open Training Data" introduction="Why we shouldn't worry so much about what data AI is training on" dim = {mousedOver != 2 && mousedOver !=0} onMouseOver={()=>dimArticles(2)}  onMouseLeave={removeDim}/>
        <ArticlePreview title="React Native vs. Flutter" introduction="In depth guide for when to use what framework" dim = {mousedOver != 3 && mousedOver !=0} onMouseOver={()=>dimArticles(3)}  onMouseLeave={removeDim}/>
        <ArticlePreview title="Welcome to my Blog" introduction="An introductory post to my blog which will cover tech news and other things" dim = {mousedOver != 4 && mousedOver !=0} onMouseOver={()=>dimArticles(4)} onMouseLeave={removeDim}/>
    </div>
</section>

<section class="w-4">
    <Timeline/>
</section>