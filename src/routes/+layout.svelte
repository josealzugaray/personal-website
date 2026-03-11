<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>



<svelte:head>
  <link rel="icon" href={favicon} />
</svelte:head>

<nav class="sticky top-0 z-50 bg-white border-b border-stone-200">
  <div class="mx-auto max-w-4xl px-12 py-5 flex items-center justify-between">

    <a href="/" class="font-serif text-base text-stone-900 hover:text-stone-500 transition-colors">
      José María Alzugaray
    </a>

    <div class="flex gap-8 text-xs font-medium tracking-widest uppercase text-stone-400">
      <a class="hover:text-stone-900 transition-colors" href="/">Home</a>
      <a class="hover:text-stone-900 transition-colors" href="/about">About</a>
      <a class="hover:text-stone-900 transition-colors" href="/CV">CV</a>
      <a class="hover:text-stone-900 transition-colors" href="/Research-Works">Research-Projects</a>
    </div>

  </div>
</nav>

<main class="mx-auto max-w-4xl px-12 py-16">
  {@render children()}
</main>