<script lang="ts">

import { MapLibre, DefaultMarker } from 'svelte-maplibre';
import { Separator } from '$lib/components/ui/separator/index.js';

  type Place = {
    name: string;
    lngLat: [number, number];
  };

const places: Place[] = [
  { name: 'Montevideo',        lngLat: [-56.1645, -34.9011] },
  { name: 'Buenos Aires',      lngLat: [-58.3816, -34.6037] },
  { name: 'Santiago de Chile', lngLat: [-70.6693, -33.4489] },
  { name: 'Rio de Janeiro',    lngLat: [-43.1729, -22.9068] },
  { name: 'Natal',             lngLat: [-35.2094,  -5.7945] },
  { name: 'Boston',            lngLat: [-71.0589,  42.3601] },
  { name: 'San Francisco',     lngLat: [-122.4194, 37.7749] },
  { name: 'Chicago',           lngLat: [-87.6298,  41.8781] },
  { name: 'Atlanta',           lngLat: [-84.3880,  33.7490] },
  { name: 'London',            lngLat: [ -0.1276,  51.5074] },
  { name: 'Edinburgh',         lngLat: [ -3.1883,  55.9533] },
  { name: 'Liverpool',         lngLat: [ -2.9916,  53.4084] },
  { name: 'Cardiff',           lngLat: [ -3.1791,  51.4816] },
  { name: 'Madrid',            lngLat: [ -3.7038,  40.4168] },
  { name: 'Paris',             lngLat: [  2.3522,  48.8566] },
  { name: 'Lyon',              lngLat: [  4.8357,  45.7640] },
  { name: 'Niza',              lngLat: [  7.2620,  43.7102] },
  { name: 'Lille',             lngLat: [  3.0573,  50.6292] },
  { name: 'Berlin',            lngLat: [ 13.4050,  52.5200] },
  { name: 'Rome',              lngLat: [ 12.4964,  41.9028] },
  { name: 'Florence',          lngLat: [ 11.2558,  43.7696] },
  { name: 'Vienna',            lngLat: [ 16.3738,  48.2082] },
  { name: 'Prague',            lngLat: [ 14.4378,  50.0755] },
  { name: 'Tokyo',             lngLat: [139.6917,  35.6895] },
  { name: 'Kyoto',             lngLat: [135.7681,  35.0116] },
  { name: 'Hiroshima',         lngLat: [132.4596,  34.3853] },
  { name: 'Bariloche',         lngLat: [-71.3103, -41.1335] },
  { name: 'Mar del Plata',     lngLat: [-57.5575, -38.0055] },
];
</script>

<svelte:head>
  <title>About — José María Alzugaray</title>
</svelte:head>

<!-- Page header -->
<div class="flex items-end justify-between pb-8 mb-8 border-b border-stone-200">
  <h1 class="font-serif text-3xl font-normal text-stone-900">
    About <em class="text-stone-400">me</em>
  </h1>
  <p class="text-xs text-stone-400 font-light text-right leading-relaxed">
    M.A. Digital Studies of Language, Culture & History<br />
    University of Chicago · Chicago, IL
  </p>
</div>

<!-- Bio -->
<section class="grid grid-cols-[1fr_280px] gap-8 mb-12">
  <div class="space-y-4">
    <p class="text-sm text-stone-600 font-light leading-relaxed">
  I grew up in Montevideo, Uruguay, the middle of three siblings. Before
  philosophy took over, I spent my adolescence playing rugby (which I still play)
   — a sport that taught me as much about losing as winning. During that time I 
   also started learning guitar, shaped early by my father's taste for rock and blues.
</p>
<p class="text-sm text-stone-600 font-light leading-relaxed">
  My first real encounter with philosophy was Plato's Republic during the IB.
  It stayed with me. I went on to study Philosophy at the Universidad de
  Montevideo, graduating <em>summa cum laude</em> in 2023, and Plato has
  remained a constant reference — I still meet regularly with a small group
  of friends to read and discuss his work.
</p>
<p class="text-sm text-stone-600 font-light leading-relaxed">
  I'm now at the University of Chicago pursuing a Master's in Digital
  Studies of Language, Culture, and History, specializing in AI and
  Language. I came to this field because AI sits at an intersection I find
  genuinely compelling: the intellectual challenge of understanding how
  machines process and represent meaning, and the practical relevance that
  comes with it. Studying Natural Language Processing this past quarter
  confirmed that — it is the most intellectually engaging subject I have
  encountered outside of philosophy itself.
</p>
  </div>

<div class="flex flex-col gap-4">
  <img
  src="/me.jpg"
  alt="Photo of me"
  class="w-full object-cover"
/>
  <p class="font-mono text-xs text-stone-400 text-center">Chicago, 2025</p>
</div>
</section>

<Separator class="my-10" />

<!-- Interests -->
<section class="mb-12">
  <p class="font-mono font-bold text-xs text-black tracking-widest uppercase mb-6">
    Interests & Hobbies
  </p>
  <div class="grid grid-cols-3 gap-6">
    {#each [
      { title: 'Playing and Listening to Music',},
      { title: 'Reading',},
      { title: 'Sports: Rugby, Running',},
      { title: 'Travel',},
      { title: 'Writing',},
      { title: 'Watches',},
    ] as interest}
      <div class="border-t border-stone-200 pt-4">
        <h3 class="font-serif text-sm font-normal text-stone-900 mb-1">{interest.title}</h3>
      
      </div>
    {/each}
  </div>
</section>

<Separator class="my-10" />

<!-- Travel map -->
<section>
  <p class="font-mono font-bold text-xs text-black tracking-widest uppercase mb-6">
    Places I've Visited
  </p>

  <MapLibre
    center={[10, 20]}
    zoom={1.2}
    class="h-[400px] w-full border border-stone-200"
    style="https://basemaps.cartocdn.com/gl/positron-gl-style/style.json"
  >
    {#each places as place}
      <DefaultMarker lngLat={place.lngLat} />
    {/each}
  </MapLibre>

</section>