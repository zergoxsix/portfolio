<template>
  <section id="heroSection" class=" bg-neutral-50 lg:bg-transparent pt-5 px-5 lg:pt-40 flex items-center justify-center">
    <div class="flex flex-wrap justify-evenly items-center gap-10">
      <img class="hero-animate w-[300px] h-[400px] lg:w-[350px] lg:h-[500px] rounded object-cover" src="/placeholder.jpeg" alt="Lubin Froeliger">

      <div class="hero-animate max-w-[480px] mx-0 lg:mx-40">
        <h1 class="text-3xl lg:text-4xl font-semibold text-sky-800">Bienvenue sur mon portfolio !</h1>
        <p class="text-xl lg:text-2xl mt-3 lg:mt-5">Je m'appelle Lubin Froeliger, j'ai 17 ans et je suis passionné par le développement web depuis maintenant deux ans, ainsi que par tout ce qui est en lien avec le numérique, la musique, les jeux vidéo, le design, etc.</p>
        <p class="mt-3 text-base lg:text-lg">Je travaille principalement avec Vue.js, Nuxt et Tailwind CSS.</p>
        <a class="mt-4 inline-flex items-center gap-2 hover:opacity-80 transition-colors" :style="{ color: 'var(--accent-light)' }" href="#portfolio">
          Mon portfolio
          <svg class="w-6 h-6" :style="{ fill: 'var(--accent-light)' }" version="1.0" xmlns="http://www.w3.org/2000/svg"
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
  <section id="portfolio" class="pt-40 bg-neutral-50 lg:bg-transparent">
    <div class="max-w-7xl mx-auto px-5">
      <h2 class="title-animate text-3xl font-semibold mb-20" :style="{ color: 'var(--text-primary)' }">Mes derniers projets</h2>

      <div class="grid grid-cols-1 lg:grid-cols-2 gap-8">

        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/portfolio.png" alt="image du projet portfolio" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet: Portfolio</h3>
            <p class="text-sm text-slate-700 mb-3">Un site vitrine responsive permettant de montrer mes derniers projets ainsi que mes compétences.</p>
            <p class="text-xs text-slate-500">Technologie : Vue.js, Nuxt, GSAP, Tailwind CSS</p>
            <button @click="openModal = 'portfolio'" class="mt-4 inline-block px-3 py-2 bg-sky-800 text-white rounded hover:bg-sky-700">Voir plus</button>
          </div>
        </article>

        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/placeholder.jpeg" alt="Capture du projet 2" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet: LerichePoesie</h3>
            <p class="text-sm text-slate-700 mb-3">Un site permettant à l'utilisateur de publier ses textes de poésie via le dashboard de Strapi simplement avec intégration front automatique.</p>
            <p class="text-xs text-slate-500">Technologie : Strapi, Vue.js, Nuxt, GSAP, Tailwind CSS</p>
            <button @click="openModal = 'leriche'" class="mt-4 inline-block px-3 py-2 bg-sky-800 text-white rounded hover:bg-sky-700">Voir plus</button>
          </div>
        </article>

        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/wp-stage.png" alt="Capture du projet 3" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet: WP_stage</h3>
            <p class="text-sm text-slate-700 mb-3">Un site web faisant office de rapport de stage de ma première période de stage de terminale</p>
            <p class="text-xs text-slate-500">Technologie : Vue, Nuxt, GSAP, Tailwind</p>
            <button @click="openModal = 'personal'" class="mt-4 inline-block px-3 py-2 bg-sky-800 text-white rounded hover:bg-sky-700">Voir plus</button>
          </div>
        </article>

        <article class="card-animate bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden">
          <img src="/placeholder.jpeg" alt="Capture du projet 4" class="w-full h-56 lg:h-64 object-cover">
          <div class="p-4">
            <h3 class="text-xl font-semibold text-sky-800 mb-2">Projet 4 — Mini-application</h3>
            <p class="text-sm text-slate-700 mb-3">Une mini-application démontrant des interactions en temps réel et une UI réactive.</p>
            <p class="text-xs text-slate-500">Technologie : Vue, WebSocket, Tailwind</p>
            <button @click="openModal = 'miniapp'" class="mt-4 inline-block px-3 py-2 bg-sky-800 text-white rounded hover:bg-sky-700">Voir plus</button>
          </div>
        </article>
      </div>
    </div>
  </section>

  <section id="competence" class="pt-40 pb-40 bg-neutral-50 lg:bg-transparent">
    <div class="max-w-7xl mx-auto px-5">
      <h3 class="text-3xl font-semibold text-sky-800 mb-20">Mes compétences</h3>

      <div class="competence-viewport">
        <div class="competence-track">
          <img src="/html.png" alt="logo d'HTML 5">
          <img src="/css.png" alt="logo CSS">
          <img src="/javascript.png" alt="logo javascript">
          <img src="/sass.png" alt="logo de sass">
          <img src="/wordpress.png" alt="logo de wordpress">
          <img src="/strapi.png" alt="logo de strapi">
          <img src="/php.png" alt="logo de php">
          <img src="/vueJs.png" alt="logo de vue js">
          <img src="/nuxt.png" alt="logo de nuxt">
          <img src="/bootstrap.png" alt="logo de bootstrap">
          <img src="/tailwind.png" alt="logo de tailwind">
        </div>
      </div>
    </div>

    <div class="max-w-7xl mx-auto px-5 mt-20">
      <p class="text-slate-700">Durant mes deux périodes de stage chez <a class="text-sky-300 underline" href="https://etienneleriche.com/">M. Étienne Leriche</a>, j'ai eu l'occasion d'apprendre de nombreuses technologies modernes telles que Nuxt.js, Tailwind CSS, WordPress, Bootstrap et Strapi, qui m'ont permis de progresser significativement dans le développement web.</p>
    </div>
  </section>
  
  <ProjectModal v-if="openModal === 'portfolio'" title="Projet: Portfolio" @close="openModal = null">
    <img src="/portfolio.png" alt="portfolio" class="w-full h-64 lg:h-[500px] object-cover mb-4">
    <p class="text-slate-700">Détails étendus du projet Portfolio : site vitrine responsive réalisé avec Nuxt, animations GSAP et Tailwind. Il a été créé pour montrer mes compétences et mes derniers projets.</p>
    <p class="mt-3 text-xs text-slate-500">Tech : Vue.js, Nuxt, GSAP, Tailwind CSS</p>
    <a class="text-white mt-6 inline-block p-2 rounded bg-sky-800" href="https://github.com/zergoxsix/portfolio">Voir le repo GitHub</a>
  </ProjectModal>

  <ProjectModal v-if="openModal === 'leriche'" title="Projet: LerichePoesie" @close="openModal = null">
    <img src="/placeholder.jpeg" alt="leriche" class="w-full h-64 lg:h-[500px] object-cover mb-4">
    <p class="text-slate-700">LerichePoesie est une plateforme collaborative dédiée à la publication de poésies. Développée avec mon maître de stage durant ma deuxième période de stage de l'année de terminale chez <a class="text-sky-300 underline" href="https://etienneleriche.com/">M. Étienne Leriche</a>, j'ai pris en charge l'intégralité du backend avec Strapi, ainsi que le développement du carrousel affichant les poésies et la génération automatique des pages. Le reste de l'interface frontend a été réalisé par mon maître de stage.</p>
    <p class="mt-3 text-xs text-slate-500">Tech : Strapi, Vue.js, Nuxt, GSAP, Tailwind CSS</p>
    <a class="text-white mt-6 inline-block p-2 rounded bg-sky-800" href="https://etienneleriche.com/">indisponible pour le moment</a>
  </ProjectModal>

  <ProjectModal v-if="openModal === 'personal'" title="Projet: WP_stage" @close="openModal = null">
  <img src="/wp-stage.png" alt="image du site wp_stage" class="w-full h-64 lg:h-[500px] object-cover mb-4">
  <p class="text-slate-700">Un site web créé lors de ma première période de stage de terminale chez <a class="text-sky-300 underline" href="https://etienneleriche.com/">M. Étienne Leriche,</a> qui a fait office de rapport de stage montrant tout ce que j'ai appris durant cette période comme Sass, Php, WordPress, Bootstrap</p>
  <p class="mt-3 text-xs text-slate-500">Tech : WordPress, PHP, Bootstrap</p>
  <a class="text-white mt-6 inline-block p-2 rounded bg-sky-800" href="/">indisponible pour le moment</a>
  </ProjectModal>

  <ProjectModal v-if="openModal === 'miniapp'" title="Projet: Mini-application" @close="openModal = null">
    <img src="/placeholder.jpeg" alt="miniapp" class="w-full h-64 lg:h-[500px] object-cover mb-4">
    <p class="text-slate-700">Une integration d'une section comme entrainement pour réviser les bases du HTML et du CSS</p>
    <p class="mt-3 text-xs text-slate-500">Tech : HTML, CSS, JS </p>
  </ProjectModal>

</template>

<script lang="ts" setup>
import { ref, watch, nextTick } from 'vue'
import ProjectModal from '~/components/ProjectModal.vue'

const { $gsap } = useNuxtApp()
const openModal = ref<string | null>(null)

watch(openModal, (newVal) => {
  if (newVal) {

    nextTick(() => {
      const modal = document.querySelector('.relative.bg-white')
      if (modal) {
        $gsap.from(modal, {
          opacity: 0,
          y: 50,
          duration: 0.8,
          ease: "power2.out"
        })
      }
    })
  }
})

onMounted(async () => {

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

  // Competence marquee GSAP
  nextTick(() => {
    const track = document.querySelector('#competence .competence-track') as HTMLElement | null
    if (track) {

      const children = Array.from(track.children)
      children.forEach((c) => track.appendChild(c.cloneNode(true)))

      const totalWidth = track.scrollWidth / 2

      $gsap.to(track, {
        x: -totalWidth,
        duration: 20,
        ease: 'none',
        repeat: -1
      })
    }
  })
})

</script>


<style scoped>
/* Competence carousel */
.competence-viewport { overflow: hidden; }
.competence-track { display: flex; gap: 1.25rem; align-items: center; width: max-content; }
.competence-track img { width: 56px; height: 56px; object-fit: contain; border-radius: 0.375rem; }
@media (min-width: 1024px) {
  .competence-track img { width: 88px; height: 88px; }
}
</style>