<script>
    let a = false
</script>
<svelte:head>
    <title>koshi.top</title>
</svelte:head>
<main class="flex h-screen justify-center text-center items-center">
    <div>
        <button on:click={() => {a = !a}} class="btn"><h1 class="autography-font text-center text-6xl">.</h1></button>
        {#if !a}
            <div class="w-full">
                <a href="/about" class="btn variant-soft-surface">About</a>
                <a href="/contact" class="btn variant-soft-surface">Contact</a>
                <!-- <a href="/works" class="btn variant-soft-surface">Works</a> -->
            </div>
        {/if}
    </div>
</main>
