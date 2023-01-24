<script>
	// @ts-nocheck

	import Footer from './Footer.svelte';
	import Header from './Header.svelte';
	import './styles.css';
</script>

<div class="app">
	<Header />

	<main>
		{#if $$slots.actions}
			<slot name="home" />
		{:else}
			<slot />
		{/if}
	</main>

	<Footer />
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
	}

	main {
		flex: 1;
		display: flex;
		flex-direction: column;
		padding: 1rem;
		width: 100%;
		margin: 0 auto;
		box-sizing: border-box;
	}

	main:global([slot='home']) {
		padding: 0rem !important;
	}
</style>
