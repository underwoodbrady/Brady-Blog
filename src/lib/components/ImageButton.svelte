<script lang="ts">
    export let title:string;
    export let onClick: () => void = () => {};
</script>

<button class="flex items-center space-x-2  bg-primary/50 rounded-full px-3 py-1 text-sm opacity-70 hover:opacity-100 duration-150 transition-opacity" on:click={onClick}>
    <slot/>
    <p class="text-neutral-100">{title}</p>
</button>