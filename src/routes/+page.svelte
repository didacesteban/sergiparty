<script>
  import Mario from "$lib/images/mario-large-up.png";
</script>

<svelte:head>
  <title>Sergi Party</title>
  <meta name="description" content="Sergi Party" />
</svelte:head>

<div class="relative max-w-3xl mx-auto">
  <div class="absolute animate-bounce">
    <img src={Mario} alt="Mario" />
  </div>
  <div class="flex flex-col text-center title mb-8 z-10 relative">
    <h1 class="uppercase whitespace-nowrap tracking-tighter mt-48">
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-red-400 to-red-600 custom-shadow custom-margin-right"
        >s</span
      >
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-green-400 to-green-600 custom-shadow custom-margin-right"
        >e</span
      >
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-yellow-400 to-yellow-600 custom-shadow custom-margin-right"
        >r</span
      >
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-blue-400 to-blue-600 custom-shadow custom-margin-right"
        >g</span
      >
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-pink-400 to-pink-600 custom-shadow custom-margin-right"
        >i</span
      >
    </h1>
    <h1>
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-gray-100 to-gray-200 tracking-tighter custom-shadow"
        >party</span
      >
    </h1>
    <h2>
      <span
        class="text-transparent bg-clip-text bg-gradient-to-b from-yellow-200 to-yellow-400 tracking-tighter custom-shadow"
        >superdespe</span
      >
    </h2>
  </div>
  <div
    class="bg-white mt-8 p-4 h-full rounded-lg border-dashed border-4 border-yellow-400 z-10 relative"
  >
    <h3 class="mb-4 text-yellow-400 uppercase">Tutorial</h3>
    <p class="mb-2 font-semibold">
      <span class="numbers">1.</span> Crea una motxilla per anar de finde
    </p>
    <p class="mb-2 font-semibold">
      <span class="numbers">2.</span> Afegeix un bañador
    </p>
    <p class="mb-2 font-semibold">
      <span class="numbers">3.</span> Estigues preparat el dissabte al matí
    </p>
    <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
      Quan arribis al checkpoint obtindràs un codi per poder continuar
    </p>

    <div class="flex flex-col items-center justify-center">
      <input
        class="mb-2 p-2 rounded-full border-dashed border-2 border-indigo-400 w-full focus:outline-none"
        type="text"
        placeholder="Codi"
      />
      <button
        type="button"
        class="mb-2 p-2 rounded-full bg-indigo-400 w-full text-white uppercase animate-pulse"
        >continuar</button
      >
    </div>
  </div>
</div>
