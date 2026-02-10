<template>
  <section id="heroSection" class="bg-slate-50 min-h-screen w-full flex items-center justify-center px-5 bg-white">
    <div class="max-w-7xl w-full flex flex-wrap justify-evenly items-center gap-10">
      <img class="hero-animate w-[300px] h-[400px] lg:w-[350px] lg:h-[500px] rounded object-cover" src="/lubin.jpg" alt="Lubin Froeliger">

      <div class="hero-animate max-w-[480px]">
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
  <section id="portfolio" class="">
    <h2 class="text-3xl font-semibold text-sky-800 pl-48">Mes dernier projet:</h2>
    <div>
      <p>Back-end et frontend du site leriche poésie</p>
    </div>
  </section>
</template>

<script lang="ts" setup>
const { $gsap } = useNuxtApp()

onMounted(() => {
  $gsap.from(".hero-animate", {
    opacity: 0,
    y: 30,
    scale: 1.05,
    duration: 1,
    ease: "power2.out",
    stagger: 0.2
  })
})
</script>

<style scoped>
.hero-animate {
  backface-visibility: hidden;
  -webkit-backface-visibility: hidden;
  transform: translateZ(0);
  -webkit-transform: translateZ(0);
}
</style>