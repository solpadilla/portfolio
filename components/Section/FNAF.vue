<template>
  <h2 class="text-[32px] my-4 font-sans font-bold">
    <nuxt-link class="flex items-center gap-1" to="https://fnafpizzaria.netlify.app" target="_blank" rel="noopener noreferrer">
      <span class="fnaf-gold flicker glow">FNAF Pizza Ordering App</span>
    </nuxt-link>
  </h2>

  <div class="relative font-raj max-w-[685px] w-full mx-auto">
    <div class="relative overflow-hidden rounded-md">
      <nuxt-link to="https://fnafpizzaria.netlify.app" target="_blank" rel="noopener noreferrer">
        <img
          v-for="i in 7"
          :key="i"
          :src="`/fnaf/fnaf-${i}.png`"
          :alt="`FNAF Pizza Screenshot ${i}`"
          class="w-full h-auto object-cover rounded-md absolute top-0 left-0 transition-opacity duration-500"
          :class="{ 'opacity-0': currentImageIndex !== i - 1, 'opacity-100': currentImageIndex === i - 1 }"
          data-not-lazy
        />
      </nuxt-link>

      <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex gap-2 z-10">
        <button
          v-for="index in 7"
          :key="index"
          @click.stop="goToImage(index - 1)"
          :class="[
            'w-2 h-2 rounded-full transition-all',
            currentImageIndex === index - 1 ? 'bg-white w-6' : 'bg-white/50 hover:bg-white/75'
          ]"
          :aria-label="`Go to image ${index}`"
        ></button>
      </div>
    </div>
  </div>

  <p class="text-center mt-6 max-w-xl">A Five Nights at Freddy's themed pizza ordering app built with Claude, featuring real-time order tracking, admin management, and Stripe payment integration with a VHS security camera aesthetic.</p>

  <div class="flex flex-col items-center my-3">
    <strong>Built with:</strong>
    <ul class="flex flex-wrap gap-2 text-center justify-center">
      <li><Icon name="simple-icons:anthropic" /> Claude AI,</li> 
      <li><Icon name="logos:nuxt-icon" /> Nuxt 3,</li>
      <li><Icon name="devicon:vuejs" /> Vue 3,</li>
      <li><Icon name="devicon:typescript" /> TypeScript,</li>
      <li><Icon name="devicon:tailwindcss" /> Tailwind CSS,</li>
      <li><Icon name="logos:pinia" /> Pinia,</li>
      <li><Icon name="simple-icons:pusher" /> Pusher,</li>
      <li><Icon name="logos:stripe" /> Stripe,</li>
      <li><Icon name="simple-icons:netlify" /> Netlify</li>
    </ul>
  </div>

  <div class="flex mt-4 gap-10">
    <nuxt-link to="https://fnafpizzaria.netlify.app" target="_blank" rel="noopener noreferrer">
      <UIButton>View Live</UIButton>
    </nuxt-link>
    <nuxt-link to="https://github.com/fnafpizza/fnaf-pizza-app" target="_blank" rel="noopener noreferrer">
      <UIButton>View Code</UIButton>
    </nuxt-link>
  </div>
</template>

<script setup>
const currentImageIndex = ref(0)
let intervalId = null

onMounted(() => {
  startSlideshow()
})

onBeforeUnmount(() => {
  stopSlideshow()
})

function startSlideshow() {
  intervalId = setInterval(() => {
    currentImageIndex.value = (currentImageIndex.value + 1) % 7
  }, 6000)
}

function stopSlideshow() {
  if (intervalId) {
    clearInterval(intervalId)
    intervalId = null
  }
}

function goToImage(index) {
  currentImageIndex.value = index
  stopSlideshow()
  startSlideshow()
}
</script>

<style scoped>
/* Ensure container has proper height */
.relative.overflow-hidden {
  position: relative;
  padding-bottom: 58.4%; /* Aspect ratio placeholder (400/685 * 100) */
}

.relative.overflow-hidden img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.fnaf-gold {
  color: #d4af37;
}

/* Glow Effect - for borders and text (subtle version) */
@keyframes glow {
  0%, 100% {
    text-shadow: 0 0 5px rgba(212, 175, 55, 0.5), 0 0 10px rgba(212, 175, 55, 0.3);
  }
  50% {
    text-shadow: 0 0 8px rgba(212, 175, 55, 0.6), 0 0 15px rgba(212, 175, 55, 0.4);
  }
}

.glow-text {
  animation: glow 3s ease-in-out infinite;
}

@keyframes flicker {
  0%, 100% { opacity: 1; }
  41% { opacity: 1; }
  42% { opacity: 0.8; }
  43% { opacity: 1; }
  45% { opacity: 0.6; }
  46% { opacity: 1; }
  82% { opacity: 0.7; }
  83% { opacity: 1; }
  87% { opacity: 0.9; }
  88% { opacity: 1; }
}

.flicker {
  animation: flicker 4s infinite;
}
</style>
