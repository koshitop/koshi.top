<script>
	import '../app.postcss';

	// Highlight JS
	import hljs from 'highlight.js/lib/core';
	import 'highlight.js/styles/github-dark.css';
	import { storeHighlightJs } from '@skeletonlabs/skeleton';
	import xml from 'highlight.js/lib/languages/xml'; // for HTML
	import css from 'highlight.js/lib/languages/css';
	import javascript from 'highlight.js/lib/languages/javascript';
	import typescript from 'highlight.js/lib/languages/typescript';

	hljs.registerLanguage('xml', xml); // for HTML
	hljs.registerLanguage('css', css);
	hljs.registerLanguage('javascript', javascript);
	hljs.registerLanguage('typescript', typescript);
	storeHighlightJs.set(hljs);

	// Floating UI for Popups
	import { computePosition, autoUpdate, flip, shift, offset, arrow } from '@floating-ui/dom';
	import { storePopup, AppShell, Drawer, initializeStores, getDrawerStore } from '@skeletonlabs/skeleton';
	storePopup.set({ computePosition, autoUpdate, flip, shift, offset, arrow });
	import Navigation from '../lib/Navigation.svelte';
	initializeStores();
	let drawerStore = getDrawerStore();
	function drawerOpen() {
		drawerStore.open({
			position: "right",
			bgDrawer: "bg-surface-600 ",
			width: "w-2/3"
		});
	}
	import { page } from '$app/stores'
</script>

{#if $page.url.pathname !== "/"}
	
<AppShell slotSidebarRight="bg-surface-600 rounded-2xl hidden fixed right-0 xl:block w-0 xl:w-64 text-right m-2 drop-shadow-lg">
    <div class="text-black text-right xl:hidden w-full" >
		<strong class="text-2xl float-left m-2">Koshi.Top</strong>
        <button class="xl:hidden btn btn-sm" on:click={drawerOpen}>
            <span>
                <svg viewBox="0 0 100 80" class="fill-token w-9 h-9">
                    <rect width="100" height="20" />
                    <rect y="30" width="100" height="20" />
                    <rect y="60" width="100" height="20" />
                </svg>
            </span>
        </button>
    </div>

	<svelte:fragment slot="sidebarRight">
		<Navigation />
	</svelte:fragment>

</AppShell>
<Drawer >
	<Navigation />
</Drawer>
{/if}
<slot />
