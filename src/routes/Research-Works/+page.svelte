<script lang="ts">
  import * as Card from '$lib/components/ui/card/index.js';

  type Category = 'all' | 'development' | 'research' | 'philosophy';

  type Inquiry = {
    title: string;
    year: string;
    category: Exclude<Category, 'all'>;
    description: string;
    tags: string[];
    link: string;
    contact?: string;
  };

//Research and development projects/works
  const inquiries: Inquiry[] = [
    {
      title: 'Corpus Analysis: Cayetana Álvarez de Toledo',
      year: '2026',
      category: 'research',
      description:
        'A computational text analysis of YouTube speech transcriptions from Spanish politician Cayetana Álvarez de Toledo. The corpus was built from cleaned and TEI-encoded transcripts, then analyzed using multiple NLP methods including topic modeling, document similarity, and clustering. Final project for Digital Texts I — currently in progress.',
      tags: ['NLP', 'TEI', 'Corpus Analysis', 'Python', 'Digital Humanities', 'In Progress'],
      link: 'https://github.com/josealzugaray/cayetana-corpus.git',
    },
    {
      title: 'Personal Website',
      year: '2026',
      category: 'development',
      description:
        'This site — built with Svelte 5, SvelteKit, TypeScript, and Tailwind. Features a MapLibre travel map, a filterable inquiries feed, and a full CV.',
      tags: ['Svelte 5', 'SvelteKit', 'TypeScript', 'Tailwind', 'MapLibre'],
      link: '',
    },
    {
      title: 'Met Museum Inventory Pages',
      year: '2026',
      category: 'development',
      description:
        'A SvelteKit app that consumes the Metropolitan Museum of Art\'s public API. Features static routes for two artworks, a keyword search with dynamic routing, and artwork detail pages displaying images, artist bios, and collection metadata.',
      tags: ['SvelteKit', 'REST API', 'Dynamic Routes', 'Vercel', 'Shadcn-svelte', 'Course Assignment'],
      link: 'https://met-museum-api.vercel.app/',
    },
    {
      title: 'OCHRE Spatial Units Explorer',
      year: '2026',
      category: 'development',
      description:
        'A SvelteKit app built on the OCHRE API from the University of Chicago. Displays a filterable table and interactive MapLibre map of spatial units, with dynamic detail pages per item. Built with shadcn-svelte Table and Input components.',
      tags: ['SvelteKit', 'OCHRE API', 'MapLibre', 'Shadcn-svelte', 'Vercel', 'Course Assignment'],
      link: 'https://week8-assignment-wheat.vercel.app/',
    },
    {
      title: 'Plato Ontology',
      year: '2025',
      category: 'development',
      description:
        'An RDF/OWL ontology mapping Plato\'s core philosophical ideas — concepts, relations, and arguments — as structured, machine-readable knowledge. Final project for Data Management.',
      tags: ['RDF', 'OWL', 'Ontology', 'Plato', 'Data Management'],
      link: 'https://github.com/josealzugaray/OWL-Ontology-/blob/main/PlatoOntology.rdf',
    },
    {
      title: 'Personhood: Between the Common and the Own',
      year: '2025',
      category: 'philosophy',
      description:
        'Chapter contribution to a collaborative volume on metaphysics and personhood, funded by the John Templeton Foundation. Co-authored with researchers from the Universidad de Montevideo and the Universidad de Salamanca.',
      tags: ['Metaphysics', 'Personhood', 'John Templeton Foundation', 'Published'],
      link: '',
    },
    {
      title: 'God as a Person',
      year: '2023',
      category: 'philosophy',
      description:
        'Collaborative research on the theological and philosophical dimensions of personhood. Contributed to international meetings, peer reviews, and a John Templeton Foundation-funded publication.',
      tags: ['Philosophy of Religion', 'Personhood', 'John Templeton Foundation', 'Published'],
      link: '',
    },
    {
      title: 'The Education Issue: Finland vs. the United States',
      year: '2019',
      category: 'research',
      description:
        'Comparative analysis of educational systems and teacher training models, published in Repórter (reporter.um.edu.uy).',
      tags: ['Education', 'Comparative Analysis', 'Published'],
      link: 'https://reporter.um.edu.uy/la-cuestion-de-la-educacion-una-comparacion-entre-finlandia-y-estados-unidos/',
    },
    {
      title: 'Human Understanding vs. Artificial "Understanding" - An Epistemological Comparison',
      year: '2026',
      category: 'philosophy',
      description:
        'Comparative paper analyzing the epistemological differences between human understanding and artificial "understanding" in AI systems. Explores concepts of knowledge, consciousness, and meaning from both philosophical and computational perspectives.',
      tags: ['Epistemology', 'AI', 'Comparative Analysis'],
      link: '',
      contact: 'Contact me for a copy of the paper'
    }
  ];

  const categories: { value: Category; label: string }[] = [
    { value: 'all',         label: 'All' },
    { value: 'development', label: 'Development' },
    { value: 'research',    label: 'Research' },
    { value: 'philosophy',  label: 'Philosophy' },
  ];

  let activeCategory: Category = $state('all');

  let filtered = $derived(
    activeCategory === 'all'
      ? inquiries
      : inquiries.filter((item) => item.category === activeCategory)
  );

  function badgeClass(category: Exclude<Category, 'all'>): string {
    if (category === 'development') return 'text-blue-800 border-blue-200 bg-blue-50';
    if (category === 'philosophy')  return 'text-amber-800 border-amber-200 bg-amber-50';
    return 'text-emerald-800 border-emerald-200 bg-emerald-50';
  }
</script>

<svelte:head>
  <title>Inquiries — José María Alzugaray</title>
</svelte:head>

<!-- Page header -->
<div class="pb-8 mb-8 border-b border-stone-200">
  <h1 class="font-serif text-3xl font-normal text-stone-900 mb-2">Projects & Inquiries</h1>
  <p class="text-sm text-stone-400 font-light max-w-xl leading-relaxed">
    A mix of technical projects, research work, and philosophical investigations —
    things built, written, or thought carefully about. More coming soon.
  </p>
</div>

<!-- Filter tabs -->
<div class="flex gap-0 border-b border-stone-200 mb-8">
  {#each categories as cat}
    <button
      onclick={() => activeCategory = cat.value}
      class="px-4 py-2 text-xs tracking-widest uppercase font-medium border-b-2 transition-colors
        {activeCategory === cat.value
          ? 'border-blue-800 text-blue-800'
          : 'border-transparent text-stone-400 hover:text-stone-900'}"
    >
      {cat.label}
    </button>
  {/each}
</div>

<!-- Inquiry grid -->

<div class="grid grid-cols-1 gap-4 sm:grid-cols-2 lg:grid-cols-3">
  {#each filtered as item, i}
    <Card.Root class="flex flex-col justify-between hover:bg-stone-50 transition-colors group">
      <Card.Header>
        <div class="flex items-start justify-between mb-2">
          <span class="font-mono text-xs text-stone-300">
            {String(i + 1).padStart(2, '0')} —
          </span>
          <span class="font-mono text-xs border px-2 py-0.5 {badgeClass(item.category)}">
            {item.category}
          </span>
        </div>
        <Card.Title class="font-serif text-base font-normal leading-snug">
          {item.title}
        </Card.Title>
        <Card.Description class="text-xs font-light leading-relaxed">
          {item.description}
        </Card.Description>
      </Card.Header>

      <Card.Footer class="flex flex-col items-start gap-3">
        <div class="flex flex-wrap gap-1.5">
          {#each item.tags as tag}
            <span class="font-mono text-xs text-stone-400 border border-stone-200 bg-stone-50 px-2 py-0.5">
              {tag}
            </span>
          {/each}
        </div>
        {#if item.link}
          <a
            href={item.link}
            target="_blank"
            class="font-mono text-xs text-blue-800 hover:underline"
          >
            View
          </a>
        {/if}
      </Card.Footer>
    </Card.Root>
  {/each}

  {#if filtered.length === 0}
    <div class="col-span-3 py-16 text-center">
      <p class="text-sm text-stone-400 font-light">Nothing here yet — check back soon.</p>
    </div>
  {/if}
</div>