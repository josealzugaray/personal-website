<script lang="ts">
  type CvEntry = {
    years: string;
    title: string;
    institution: string;
    description: string;
  };

  const education: CvEntry[] = [
    {
      years: '2025–Present',
      title: 'M.A. Digital Studies of Language, Culture & History',
      institution: 'University of Chicago · Chicago, IL',
      description: 'AI and Language specialization.',
    },
    {
      years: '2019–2023',
      title: 'B.A. Philosophy',
      institution: 'Universidad de Montevideo · Montevideo, Uruguay',
      description: 'Graduated Summa Cum Laude.',
    },
    {
      years: 'Feb–Sep 2023',
      title: 'Diploma in Digital Marketing & Data Analytics',
      institution: 'Senpai Academy',
      description: 'Data analysis, performance metrics, and algorithmic tools for digital campaign optimization.',
    },
    {
      years: 'Feb–Sep 2023',
      title: 'Diploma in Economics Fundamentals',
      institution: 'Universidad de Montevideo',
      description: 'Microeconomics, Macroeconomics, International trade and markets.',
    },
  ];

  const research: CvEntry[] = [
    {
      years: 'Sept 2025 – Dec 2025',
      title: 'Participant, AI Branch — Existential Risk Laboratory',
      institution: 'University of Chicago',
      description: 'Weekly discussions on AI safety, alignment, and reasoning challenges in advanced AI systems. Study of LLM behavior, failure modes, and agentic AI.',
    },
    {
      years: 'Mar 2024–Apr 2025',
      title: 'Researcher — Personhood: Between the Common and the Own',
      institution: 'Universidad de Montevideo & Universidad de Salamanca',
      description: 'Contributed a chapter and peer-reviewed additional chapters. Publication funded by the John Templeton Foundation, released March 2025.',
    },
    {
      years: 'Feb–Dec 2023',
      title: 'Researcher — God as a Person',
      institution: 'Universidad de Montevideo & Universidad de Salamanca',
      description: 'Coordinated international meetings and peer reviews. Collaborative publication funded by the John Templeton Foundation.',
    },
  ];

  const teaching: CvEntry[] = [
    {
      years: 'Dec 2024–Aug 2025',
      title: 'Lecturer — Fundamental Philosophy Questions',
      institution: 'Universidad Católica del Uruguay',
      description: 'Undergraduate courses on ethics, metaphysics, and meaning.',
    },
    {
      years: 'Dec 2024–Jul 2025',
      title: 'Lecturer — Philosophical Anthropology',
      institution: 'Universidad de Montevideo',
      description: 'Courses exploring human nature, culture, and ethics.',
    },
    {
      years: 'Feb–Aug 2024',
      title: 'Teaching Assistant — Ethics',
      institution: 'Universidad de Montevideo',
      description: 'Virtue, justice, and moral philosophy (Aristotle, MacIntyre, Kant).',
    },
    {
      years: 'Aug–Dec 2024',
      title: 'Teaching Assistant — Science and Religion in Dialogue',
      institution: 'Universidad Católica del Uruguay',
      description: 'Interdisciplinary debates on the philosophical implications of scientific inquiry.',
    },
    {
      years: 'Aug–Dec 2023',
      title: 'Teaching Assistant — Contemporary Philosophy',
      institution: 'Universidad de Montevideo',
      description: 'Courses linking philosophy, linguistics, and cognitive science.',
    },
  ];

  const languages = ['Spanish (Native)', 'English (Advanced)', 'Portuguese (Intermediate)', 'Latin (Beginner)'];
  const technical = ['Python', 'SQLite', 'HTML', 'Cypher', 'Svelte 5', 'TypeScript', 'Tailwind', 'Data Analysis'];
</script>

<svelte:head>
<title> CV – José María Alzugaray</title>
</svelte:head>

<!-- Page header -->
<div class="flex items-start justify-between pb-8 mb-8 border-b border-stone-200">
  <div>
    <h1 class="font-serif text-3xl font-normal text-stone-900">Curriculum Vitæ</h1>
    <p class="text-xs text-stone-400 font-light mt-1">José María Alzugaray · Updated 2026</p>
  </div>
  
</div>

<!-- Education -->
<section class="mb-10">
  <h2 class="font-mono text-xl text-stone-400 tracking-widest uppercase mb-4 pb-3 border-b border-stone-100">
    Education
  </h2>
  {#each education as entry}
    <div class="grid grid-cols-1 gap-2 py-4 border-b border-stone-100 sm:grid-cols-[130px_1fr] sm:gap-8">
      <span class="font-mono text-xs text-stone-400 pt-0.5 leading-relaxed">{entry.years}</span>
      <div>
        <p class="text-sm font-medium text-stone-900 mb-0.5">{entry.title}</p>
        <p class="text-xs text-blue-800 font-light mb-1">{entry.institution}</p>
        <p class="text-xs text-stone-500 font-light leading-relaxed">{entry.description}</p>
      </div>
    </div>
  {/each}
</section>

<!-- Research -->
<section class="mb-10">
  <h2 class="font-mono text-xl text-stone-400 tracking-widest uppercase mb-4 pb-3 border-b border-stone-100">
    Research
  </h2>
  {#each research as entry}
    <div class="grid grid-cols-1 gap-2 py-4 border-b border-stone-100 sm:grid-cols-[130px_1fr] sm:gap-8">
      <span class="font-mono text-xs text-stone-400 pt-0.5 leading-relaxed">{entry.years}</span>
      <div>
        <p class="text-sm font-medium text-stone-900 mb-0.5">{entry.title}</p>
        <p class="text-xs text-blue-800 font-light mb-1">{entry.institution}</p>
        <p class="text-xs text-stone-500 font-light leading-relaxed">{entry.description}</p>
      </div>
    </div>
  {/each}
</section>

<!-- Teaching -->
<section class="mb-10">
  <h2 class="font-mono text-xl text-stone-400 tracking-widest uppercase mb-4 pb-3 border-b border-stone-100">
    Teaching
  </h2>
  {#each teaching as entry}
    <div class="grid grid-cols-1 gap-2 py-4 border-b border-stone-100 sm:grid-cols-[130px_1fr] sm:gap-8">
      <span class="font-mono text-xs text-stone-400 pt-0.5 leading-relaxed">{entry.years}</span>
      <div>
        <p class="text-sm font-medium text-stone-900 mb-0.5">{entry.title}</p>
        <p class="text-xs text-blue-800 font-light mb-1">{entry.institution}</p>
        <p class="text-xs text-stone-500 font-light leading-relaxed">{entry.description}</p>
      </div>
    </div>
  {/each}
</section>

<!-- Skills & Languages -->
<section class="mb-10">
  <h2 class="font-mono text-xl text-stone-400 tracking-widest uppercase mb-4 pb-3 border-b border-stone-100">
    Skills & Languages
  </h2>

  <div class="grid grid-cols-[130px_1fr] gap-8 py-4 border-b border-stone-100">
    <span class="font-mono text-xs text-stone-400 pt-0.5">Technical</span>
    <div class="flex flex-wrap gap-2">
      {#each technical as skill}
        <span class="font-mono text-xs text-stone-500 border border-stone-200 px-2 py-1 bg-stone-50">
          {skill}
        </span>
      {/each}
    </div>
  </div>

  <div class="grid grid-cols-[130px_1fr] gap-8 py-4">
    <span class="font-mono text-xs text-stone-400 pt-0.5">Languages</span>
    <div class="flex flex-wrap gap-2">
      {#each languages as lang}
        <span class="font-mono text-xs text-stone-500 border border-stone-200 px-2 py-1 bg-stone-50">
          {lang}
        </span>
      {/each}
    </div>
  </div>
</section>