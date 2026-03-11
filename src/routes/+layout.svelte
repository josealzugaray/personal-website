<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>



<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>


<nav class="sticky top-0 z-50 bg-white border-b border-stone-200">
  <div class="mx-auto max-w-4xl px-4 py-4 flex flex-col gap-4 sm:px-8 sm:py-5 sm:flex-row sm:items-center sm:justify-between">
    <a href="/" class="font-serif text-base text-stone-900 hover:text-stone-500 transition-colors">
      José María Alzugaray
    </a>

    <div class="flex flex-wrap gap-4 text-xs font-medium tracking-widest uppercase text-stone-400 sm:gap-8">
      <a class="hover:text-stone-900 transition-colors" href="/">Home</a>
      <a class="hover:text-stone-900 transition-colors" href="/about">About</a>
      <a class="hover:text-stone-900 transition-colors" href="/CV">CV</a>
      <a class="hover:text-stone-900 transition-colors" href="/Research-Works">Research-Projects</a>
    </div>
  </div>
</nav>


<main class="mx-auto max-w-4xl px-4 py-8 sm:px-8 sm:py-12 lg:px-12 lg:py-16">
  {@render children()}
</main>