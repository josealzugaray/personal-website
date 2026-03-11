<script lang="ts">
  const recentWork = [
    { title: 'Personhood: Between the Common and the Own', year: '2025' },
    { title: 'God as a Person (John Templeton Foundation)', year: '2023' },
    { title: 'Plato RDF Ontology', year: '2025' },
    { title: 'The Education Issue: Finland vs. USA', year: '2019' },
  ];

   import { Mail, Linkedin, Github } from 'lucide-svelte';
</script>

<svelte:head>
  <title>José María Alzugaray</title>
</svelte:head>


<section class="pt-4 pb-18 border-b border-stone-200">

  <h1 class="font-serif text-5xl font-normal text-stone-900 leading-tight mb-6">
    José María Alzugaray<br />
    <em class="text-stone-400">Philosopher & Digital Scholar</em>
  </h1>

  <p class="text-stone-500 text-base font-light leading-relaxed max-w-xl mb-10">
    Graduate student at the University of Chicago, studying Digital Studies
    of Language, Culture, and History with a specialization in AI and Language.
    My work moves between philosophy and digital humanities.
  </p>

<div class="border border-stone-300 p-6 inline-flex flex-col gap-3 mt-2 min-w-64">
  <p class="font-mono text-xs text-stone-900 tracking-widest uppercase mb-1">Contact</p>
  
  <a
    href="mailto:jmalzugaray@uchicago.edu"
    class="font-mono text-sm text-stone-700 hover:text-blue-800 transition-colors flex items-center gap-2"
  >
    <Mail size={14} />
    jmalzugaray@uchicago.edu
  </a>
  <a
    href="https://linkedin.com/in/YOURHANDLE"
    target="_blank"
    class="font-mono text-sm text-stone-700 hover:text-blue-800 transition-colors flex items-center gap-2"
  >
    <Linkedin size={14} />
    linkedin.com/in/josemariaalzugaray/
  </a>
  <a
    href="https://github.com/josealzugaray"
    target="_blank"
    class="font-mono text-sm text-stone-700 hover:text-blue-800 transition-colors flex items-center gap-2"
  >
    <Github size={14} />
    github.com/josealzugaray
  </a>
</div>


</section>

<!-- Two-column section -->
<section class="pt-12 grid grid-cols-2 gap-16">

  <!-- Recent work -->
  <div>
    <p class="font-mono text-xs text-stone-400 tracking-widest uppercase mb-5">
      Recent Work
    </p>
    <ul>
      {#each recentWork as item}
        <li class="flex justify-between py-3 border-b border-stone-100 text-sm text-stone-500 font-light">
          <span>{item.title}</span>
          <span class="font-mono text-xs text-stone-400 self-center pl-4 flex-none">{item.year}</span>
        </li>
      {/each}
    </ul>
    <a href="/Research-Works" class="inline-block mt-4 text-xs text-blue-800 font-medium hover:underline">
      All inquiries →
    </a>
  </div>

  <!-- About  -->
  <div>
    <p class="font-mono text-xs text-stone-400 tracking-widest uppercase mb-5">
      About
    </p>
    <h3 class="font-serif text-lg font-normal text-stone-900 mb-3">
      Philosophy meets computation
    </h3>
    <p class="text-sm text-stone-500 font-light leading-relaxed">
      From Montevideo to Chicago, I've been drawn to the hardest questions —
      about persons, minds, and what it means to know. Now I'm asking those
      same questions about machines and what it implies for human life as we 
      know it.
    </p>
    <a href="/about" class="inline-block mt-4 text-xs text-blue-800 font-medium hover:underline">
      Read more →
    </a>
  </div>

</section>