<script lang="ts">
    export let placeholder:string;
    import Magnify from 'virtual:icons/mdi/magnify';

</script>

<div class="relative border-light/20 border-2 bg-light/10 rounded-full px-2 py-1">
    <Magnify width={20} height={20} class="text-neutral-400"/>
    <input class="absolute left-0 top-0 w-full h-full rounded-full bg-transparent pl-8 outline-none placeholder:text-neutral-400 text-neutral-100" placeholder={placeholder}/>
</div>