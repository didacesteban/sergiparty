<script>
  // @ts-nocheck

  import Mario from "$lib/images/mario-large-up.png";
  import Alba from "$lib/images/alba.png";
  import Cloth from "$lib/images/cloth.jpg";
  import Mistery from "$lib/images/mistery.webp";
  import Bowser from "$lib/images/bowser.png";
  import Star from "$lib/images/star.webp";

  let showCloth = false;
  let chupito = false;
  let level = 0;
  let racha = 0;
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
    {#if level === 0 && !chupito && racha !== 3}
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
          id="codi"
          class="mb-2 p-2 rounded-full border-dashed border-2 border-indigo-400 w-full focus:outline-none"
          type="text"
          placeholder="Codi"
        />
        <button
          type="button"
          on:click={() => {
            if (document.getElementById("codi").value === "1234") {
              level = 1;
            }
          }}
          class="mb-2 p-2 rounded-full bg-indigo-400 w-full text-white uppercase animate-pulse"
          >continuar</button
        >
      </div>
    {/if}
    {#if level === 1 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">Som-hi!</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Fes click per obtenir els poders
      </p>
      <button type="button" on:click={() => (showCloth = true)}>
        <img src={showCloth ? Cloth : Mistery} alt="cloth" />
      </button>
      {#if showCloth}
        <div class="flex flex-col items-center justify-center mt-2">
          <button
            type="button"
            on:click={() => {
              level = 2;
            }}
            class="mb-2 p-2 rounded-full bg-indigo-400 w-full text-white uppercase animate-pulse"
            >continuar</button
          >
        </div>
      {/if}
    {/if}
    {#if level === 2 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 1</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Asignatura preferida de l’alba a l’escola
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => {
            level = 3;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Plàstica</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Bio</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Eduacació Física</button
        >
      </div>
    {/if}
    {#if level === 3 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 2</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Primera peli que veu veure junts al cine
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Alguna de pixar</button
        >
        <button
          type="button"
          on:click={() => {
            level = 4;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >No en te ni idea</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Alguna de sustos</button
        >
      </div>
    {/if}
    {#if level === 4 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 3</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Com seria el seu lloc ideal per viure
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >platja</button
        >
        <button
          type="button"
          on:click={() => {
            level = 5;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Que mai fes pluja</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >muntanya</button
        >
      </div>
    {/if}
    {#if level === 5 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 4</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Segons cognoms dels pares de l’alba
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Figueras / Rodriguez</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Higueras / Martinez</button
        >
        <button
          type="button"
          on:click={() => {
            level = 6;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Higueras / Rodriguez</button
        >
      </div>
    {/if}
    {#if level === 6 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 5</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Si hagués de triar entre no tornar a Sabadell mai més o no tornar a
        Talamanca, que triaria?
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => {
            level = 7;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >No tornar a Sabadell</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >No tornar a Talamanca</button
        >
      </div>
    {/if}
    {#if level === 7 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 6</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Quin dia i mes va neixer el teu fillastre Swing
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => {
            level = 8;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >24/04</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >25/04</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >24/05</button
        >
      </div>
    {/if}
    {#if level === 8 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 7</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Quants tattos porta l’Alba
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => {
            level = 9;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >7</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >6</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >9</button
        >
      </div>
    {/if}
    {#if level === 9 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 8</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Si pogues apendre un idioma sense haver d’estudiar quin seria
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Angles</button
        >
        <button
          type="button"
          on:click={() => {
            level = 10;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Frances</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >japones</button
        >
      </div>
    {/if}
    {#if level === 10 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">World 9</h3>
      <p class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Cantant preferit
      </p>

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Rusowsky</button
        >
        <button
          type="button"
          on:click={() => (chupito = true)}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >guitarricadelafuente</button
        >
        <button
          type="button"
          on:click={() => {
            level = 11;
            racha = racha + 1;
          }}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >Carlos Sadness</button
        >
      </div>
    {/if}
    {#if level === 11 && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">BOSS FINAL</h3>
      <div class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        Try Not To Laugh Challenge tots JUNTS!!!
        <p>
          * Tots ens posarem aigua a la boca, guanya l'últim que aguanti tota
          l'aigua, els que la tirin CHUPITO
        </p>
      </div>

      <iframe
        width="100%"
        height="315"
        src="https://www.youtube.com/embed/T5NV0fy_cFg?si=FDHIPbluArwkBHNn"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        allowfullscreen
      />

      <div class="flex flex-col items-center justify-center mt-2 space-y-4">
        <button
          type="button"
          on:click={() => (level = "alba")}
          class="mb-2 px-2 py-6 rounded-lg bg-indigo-400 w-full text-white uppercase"
          >continuar</button
        >
      </div>
    {/if}
    {#if level === "alba" && !chupito && racha !== 3}
      <h3 class="mb-2 text-yellow-400 uppercase">Enhorabona!!</h3>
      <p class="mb-2 font-semibold">
        Has salvat a la princesa.... &#128527; &#128527;
      </p>
      <img src={Alba} alt="alba" />

      <div class="flex flex-col items-center justify-center">
        <button
          type="button"
          on:click={() => {
            level = 0;
            showCloth = false;
            chupito = false;
          }}
          class="mb-2 p-2 rounded-full bg-indigo-400 w-full text-white uppercase animate-pulse"
          >The end</button
        >
      </div>
    {/if}
    {#if chupito}
      <h3 class="mb-2 text-yellow-400 uppercase">CHUPITO!!</h3>
      <img src={Bowser} alt="bowser" />

      <div class="flex flex-col items-center justify-center mt-4">
        <button
          type="button"
          on:click={() => {
            chupito = false;
            racha = 0;
          }}
          class="mb-2 p-2 rounded-full bg-indigo-400 w-full text-white uppercase animate-pulse"
          >Seguim</button
        >
      </div>
    {/if}
    {#if racha === 3}
      <h3 class="mb-2 text-yellow-400 uppercase">PREMI!!</h3>
      <div class="mb-4 text-center p-4 bg-gray-200 rounded-lg">
        3 punts seguits. Pots regalar un chupito a qui vulguis!
      </div>
      <img src={Star} alt="Star" />

      <div class="flex flex-col items-center justify-center mt-4">
        <button
          type="button"
          on:click={() => (racha = 0)}
          class="mb-2 p-2 rounded-full bg-indigo-400 w-full text-white uppercase animate-pulse"
          >Seguim</button
        >
      </div>
    {/if}
  </div>
</div>
