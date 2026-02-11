<template>
  <nav class="relative flex py-5 justify-evenly bg-neutral-50 items-center text-sky-800 z-50 w-full before:absolute before:inset-0 before:bg-[url('/pattern.jpg')] before:bg-repeat before:bg-[size:150px_150px] before:opacity-5 before:-z-10">
    <img src="/logo.svg" alt="logo du site">

    <div id="menue" class="flex gap-20 text-lg bg-white lg:bg-transparent max-lg:z-0 max-lg:border-2 max-lg:rounded max-lg:flex-col max-lg:fixed max-lg:top-20 max-lg:right-0 max-lg:h-screen max-lg:w-64 max-lg:pt-24 max-lg:px-8 max-lg:items-center">
      <a class="menue-link max-lg:p-2" href="/" @click="menueShow && toggleMenue()">Accueil</a>
      <a class="menue-link max-lg:p-2" href="#portfolio" @click="menueShow && toggleMenue()">Portfolio</a>
      <a class="menue-link max-lg:p-2" href="/" @click="menueShow && toggleMenue()">À propos</a>
      <a class="menue-link text-white max-lg:p-2 max-lg:rounded lg:hidden bg-sky-800" href="/" @click="menueShow && toggleMenue()">Contact</a>
    </div>
    
    <svg id="menueButton" @click="toggleMenue" class="max-lg:z-20 fill-gray-300 lg:hidden" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64" width="48px" height="48px"><path d="M51 46c1.104 0 2 .895 2 2 0 1.105-.896 2-2 2-.601 0-37.399 0-38 0-1.104 0-2-.895-2-2 0-1.105.896-2 2-2C13.601 46 50.399 46 51 46zM51 30c1.104 0 2 .895 2 2 0 1.105-.896 2-2 2-.601 0-37.399 0-38 0-1.104 0-2-.895-2-2 0-1.105.896-2 2-2C13.601 30 50.399 30 51 30zM51 14c1.104 0 2 .895 2 2 0 1.105-.896 2-2 2-.601 0-37.399 0-38 0-1.104 0-2-.895-2-2 0-1.105.896-2 2-2C13.601 14 50.399 14 51 14z"/></svg>
    
    <a class="hidden text-white lg:block bg-sky-800 px-4 py-2 rounded" href="/">Contact</a>
  </nav>
</template>

<script lang="ts" setup>
const { $gsap } = useNuxtApp()
const menueShow = ref(false)
const isMobile = ref(false)

// Configuration GSAP
const GSAP_CONFIG = {
  menu: {
    offscreen: { x: '100vw' },
    onscreen: { x: 0, duration: 0.6, ease: 'power2.out' },
    offscreenOut: { x: '100vw', duration: 0.6, ease: 'power2.in' }
  },
  link: {
    hidden: { x: 30, opacity: 0 },
    visible: { x: 0, opacity: 1, stagger: 0.08, duration: 0.45 },
    hidingOut: { x: 30, opacity: 0, stagger: 0.06, duration: 0.25, ease: 'power2.in' }
  },
  button: {
    open: { rotate: -90, duration: 0.4 },
    close: { rotate: 0, duration: 0.4 }
  }
}

const initializeMenuState = (matches: boolean) => {
  if (matches) {
    $gsap.set('#menue', GSAP_CONFIG.menu.offscreen)
    $gsap.set('.menue-link', GSAP_CONFIG.link.hidden)
  } else {
    $gsap.set('#menue', { clearProps: 'all' })
    $gsap.set('.menue-link', { clearProps: 'all' })
    menueShow.value = false
  }
}

const handleMediaQuery = (e: MediaQueryListEvent | MediaQueryList) => {
  const matches = 'matches' in e ? e.matches : false
  isMobile.value = matches
  initializeMenuState(matches)
}

onMounted(() => {
  const mq = window.matchMedia('(max-width: 1023px)')
  
  handleMediaQuery(mq)

  if (mq.addEventListener) {
    mq.addEventListener('change', handleMediaQuery)
    onBeforeUnmount(() => mq.removeEventListener('change', handleMediaQuery))
  } else {
    mq.addListener(handleMediaQuery)
    onBeforeUnmount(() => mq.removeListener(handleMediaQuery))
  }
})

const toggleMenue = () => {
  if (!isMobile.value) return

  const tl = $gsap.timeline()

  if (!menueShow.value) {
    menueShow.value = true
    document.body.style.overflow = 'hidden'
    
    tl.to('#menueButton', GSAP_CONFIG.button.open)
      .to('#menue', GSAP_CONFIG.menu.onscreen, '-=0.35')
      .to('.menue-link', GSAP_CONFIG.link.visible, '-=0.35')
  } else {
    menueShow.value = false
    document.body.style.overflow = ''
    
    tl.to('#menueButton', GSAP_CONFIG.button.close)
      .to('.menue-link', GSAP_CONFIG.link.hidingOut, '-=0.35')
      .to('#menue', GSAP_CONFIG.menu.offscreenOut, '-=0.1')
  }
}
</script>

<style>
span {
  font-family: "DM Serif Text", serif;
}
</style>