<script>
    let works = [{
        title: `Tiệm nạp hộ "NGƯỜI NGHIỆN"`,
        url: "https://nguoinghien.koshi.top",
        image: ""
    }]
</script>
<svelte:head>
    <title>koshi.top | Works</title>
</svelte:head>
<main class="text-center justify-center items-center flex h-screen overflow-hidden">
    <div>
        <span class="h1">Our works:</span>
        <div class="text-center justify-center items-center flex">
            <div class="min-w-[30vw] max-w-[30vw] justify-center text-center items-center align-middle">
                <div class="m-auto">
                    <div class="snap-x scroll-px-4 snap-mandatory scroll-smooth flex gap-4 overflow-x-auto px-4 py-10">
                        {#each works as work}
                            <a href={work.url} class="snap-center shrink-0 card py-20 w-40 md:w-80">
                                <header>
                                    {work.title}
                                </header>
                                {#if work.image !== ""}
                                    <img src={work.image} alt="">
                                {/if}
                            </a>
                        {/each}
                    </div>
                </div>
            </div>
        </div> <br>
        <span class="h2">Our feedbacks:</span>
        <div class="text-center justify-center items-center flex">
            <div class="min-w-[30vw] max-w-[30vw] justify-center text-center items-center align-middle">
                <div class="m-auto">
                    <div class="snap-x scroll-px-4 snap-mandatory scroll-smooth flex gap-5 overflow-x-auto px-4 py-10">
                        {#each Array.from({ length: 1 }) as _, i}
                            <div class="snap-center shrink-0 card py-20 w-40 md:w-80 text-center">{i + 1}</div>
                        {/each}
                    </div>
                </div>
            </div>
        </div>
    </div>
</main>