<template>
  <section id="heroSection" class=" bg-neutral-50 pt-5 px-5 lg:pt-40 flex items-center justify-center">
    <div class="flex flex-wrap justify-evenly items-center gap-10">
      <img class="hero-animate w-[300px] h-[400px] lg:w-[350px] lg:h-[500px] rounded object-cover" src="/lubin.jpg" alt="Lubin Froeliger">

      <div class="hero-animate max-w-[480px] mx-0 lg:mx-40">
        <h1 class="text-3xl lg:text-4xl font-semibold text-sky-800">Bienvenue sur mon portfolio !</h1>
        <p class="text-xl text-slate-700 lg:text-2xl mt-3 lg:mt-5">Je m'appelle Lubin Froeliger, j'ai 17 ans et je suis passionné par le développement web depuis deux ans. J'aime passé mes journée a codé !</p>
        <p class="mt-3 text-slate-700 text-base lg:text-lg">Je travaille principalement avec Vue.js, Nuxt et Tailwind CSS.</p>
        <a class="mt-4 inline-flex items-center gap-2 text-sky-300 hover:text-sky-400 transition-colors" href="/">
          Mon portfolio
          <svg class="w-6 h-6 fill-sky-300" version="1.0" xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 1280.000000 640.000000"
            preserveAspectRatio="xMidYMid meet">
            <g transform="translate(0.000000,640.000000) scale(0.100000,-0.100000)" stroke="none">
            <path d="M9280 5934 c-106 -21 -223 -80 -293 -150 -99 -97 -148 -196 -168
            -336 -10 -72 -9 -97 5 -164 22 -108 75 -212 144 -282 33 -33 391 -297 851
            -627 l794 -570 -5084 -5 c-4763 -5 -5087 -6 -5132 -22 -146 -52 -265 -152
            -330 -275 -114 -217 -77 -472 93 -644 70 -71 126 -108 217 -142 l58 -22 5078
            -5 5078 -5 -752 -615 c-414 -338 -776 -638 -804 -667 -29 -29 -68 -84 -89
            -125 -112 -224 -73 -470 105 -649 104 -105 233 -159 382 -159 99 0 186 22 270
            68 70 39 2847 2303 2942 2399 160 162 199 422 93 633 -46 94 -119 163 -324
            311 -1086 782 -2701 1940 -2747 1970 -83 54 -166 80 -272 84 -49 2 -101 1
            -115 -1z"/>
            </g>
          </svg>
        </a>
      </div>
    </div>
  </section>
  <section id="portfolio" class="pt-40 bg-neutral-50">
    <div class="max-w-7xl mx-auto px-5">
      <h2 class="title-animate text-3xl font-semibold text-sky-800 mb-20">Mes derniers projets</h2>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
        <!-- Exemple de carte 1 -->
        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/portfolio.png" alt="image du projet portfolio" class="w-full h-56 lg:h-64 object-fit">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet: Portfolio</h3>
            <p class="text-sm text-slate-700 mb-3">Un site vitrine responsive permettant de montrer mes dernier projet ainsie que mes competence.</p>
            <p class="text-xs text-slate-500">Technos : Vue.js, Nuxt, GSAP, Tailwind CSS</p>
          </div>
        </article>

        <!-- Exemple de carte 2 -->
        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/placeholder.jpeg" alt="Capture du projet 2" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet: LerichePoesie</h3>
            <p class="text-sm text-slate-700 mb-3">Un site permettant a l'utilisateur de publier ces text de poésie via le dashboard de Strapi.</p>
            <p class="text-xs text-slate-500">Technos : Strapi, Vue.js, Nuxt, GSAP, Tailwind CSS</p>
          </div>
        </article>

        <!-- Exemple de carte 3 -->
        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/placeholder.jpeg" alt="Capture du projet 3" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet 3 — Portfolio personnel</h3>
            <p class="text-sm text-slate-700 mb-3">Mon portfolio personnel contenant mes réalisations et coordonnées, optimisé pour la performance.</p>
            <p class="text-xs text-slate-500">Technos : Vue, Nuxt, GSAP, Tailwind</p>
          </div>
        </article>

        <!-- Exemple de carte 4 -->
        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/placeholder.jpeg" alt="Capture du projet 4" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet 4 — Mini-application</h3>
            <p class="text-sm text-slate-700 mb-3">Une mini-application démontrant des interactions en temps réel et une UI réactive.</p>
            <p class="text-xs text-slate-500">Technos : Vue, WebSocket, Tailwind</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>

<script lang="ts" setup>
const { $gsap } = useNuxtApp()

onMounted(async () => {
  // ✅ Force le scroll en haut au chargement
  window.scrollTo(0, 0)

  const { ScrollTrigger } = await import('gsap/ScrollTrigger')
  $gsap.registerPlugin(ScrollTrigger)

  $gsap.from(".hero-animate", {
    opacity: 0,
    y: 30,
    scale: 1.05,
    duration: 1,
    ease: "power2.out",
    stagger: 0.2
  })

  $gsap.from(".title-animate", {
    opacity: 0,
    y: 30,
    duration: 0.8,
    scrollTrigger: {
      trigger: ".title-animate",
      start: "top 80%",
      toggleActions: "play none none none"
    }
  })

  $gsap.from(".card-animate", {
    opacity: 0,
    y: 50,
    duration: 0.8,
    stagger: 0.2,
    scrollTrigger: {
      trigger: ".card-animate",
      start: "top 85%",
      toggleActions: "play none none none"
    }
  })
})
</script>

<style scoped>
</style>