<script lang="ts">
	import '../app.css';

    let highlightEl:HTMLDivElement;

    function handleMousemove(e:MouseEvent){
        highlightEl.style.left = `${e.clientX}px` ;
        highlightEl.style.top = `${e.clientY}px`;
    }

</script>

<svelte:window on:mousemove={handleMousemove}/>

<section class="p-16 max-w-7xl mx-auto">
    <div class="fixed w-[800px] h-[800px] rounded-full bg-radient-ellipse-c from-primary/50 from-0% to-background to-70% -translate-x-1/2 -translate-y-1/2 " bind:this={highlightEl}></div>
    <div class=" z-10 fixed top-0 left-0 w-screen h-screen bg-background/50"></div>
    <main class="z-20 relative flex">
        <slot />

    </main>
</section>
