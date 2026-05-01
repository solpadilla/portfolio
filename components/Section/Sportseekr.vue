<template>
  <h2 class="text-[32px] my-4 font-sans font-bold">
    <nuxt-link class="flex items-center" to="https://sportseekr.netlify.app" target="_blank" rel="noopener noreferrer">
      <span>Sport</span><span class="gradient-sweep">seekr</span>
    </nuxt-link>
  </h2>

  <div class="relative font-raj max-w-[685px] w-full mx-auto">
    <div class="relative overflow-hidden rounded-md shadow-[0_0_0_1px_rgba(249,115,22,0.15)] dark:shadow-[0_0_0_1px_rgba(249,115,22,0.35),0_0_30px_-8px_rgba(249,115,22,0.25)]">
      <nuxt-link to="https://sportseekr.netlify.app" target="_blank" rel="noopener noreferrer">
        <img
          v-for="i in 5"
          :key="i"
          :src="`/sportseekr/sportseekr-${i}.png`"
          :alt="`Sportseekr Screenshot ${i} of 5`"
          class="w-full h-auto object-cover rounded-md absolute top-0 left-0 transition-opacity duration-500"
          :class="{ 'opacity-0': currentImageIndex !== i - 1, 'opacity-100': currentImageIndex === i - 1 }"
          data-not-lazy
        />
      </nuxt-link>

      <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex gap-2 z-10">
        <button
          v-for="index in 5"
          :key="index"
          @click.stop="goToImage(index - 1)"
          :class="[
            'w-2 h-2 rounded-full transition-all',
            currentImageIndex === index - 1 ? 'bg-orange-500 w-6' : 'bg-white/50 hover:bg-white/75'
          ]"
          :aria-label="`Go to image ${index}`"
        ></button>
      </div>
    </div>
  </div>

  <p class="text-center mt-6 max-w-xl">A multi-tenant SaaS platform connecting parents, athletes, coaches, and youth-sports organizations — featuring Stripe Connect payouts, native iOS/Android via Capacitor, and a Prisma + PostgreSQL backend.</p>

  <div class="flex flex-col items-center my-3">
    <strong>Built with:</strong>
    <ul class="flex flex-wrap gap-2 text-center justify-center">
      <li><Icon name="logos:nuxt-icon" /> Nuxt 3,</li>
      <li><Icon name="devicon:vuejs" /> Vue 3,</li>
      <li><Icon name="devicon:typescript" /> TypeScript,</li>
      <li><Icon name="devicon:tailwindcss" /> Tailwind CSS,</li>
      <li><Icon name="logos:pinia" /> Pinia,</li>
      <li><Icon name="logos:prisma" /> Prisma,</li>
      <li><Icon name="logos:postgresql" /> PostgreSQL,</li>
      <li><Icon name="logos:stripe" /> Stripe Connect,</li>
      <li><Icon name="simple-icons:capacitor" /> Capacitor,</li>
      <li><Icon name="simple-icons:netlify" /> Netlify</li>
    </ul>
  </div>

  <div class="flex mt-4 justify-center">
    <nuxt-link to="https://sportseekr.netlify.app" target="_blank" rel="noopener noreferrer">
      <UIButton>View Live</UIButton>
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
  // Honor user's reduced-motion preference: skip auto-advance; manual dot
  // navigation still works because goToImage() updates currentImageIndex
  // before calling startSlideshow(). `window` is implicitly client-only
  // inside onMounted, but the typeof guard keeps the component safe under
  // any future SSR-time invocation.
  if (typeof window !== 'undefined') {
    const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches
    if (prefersReducedMotion) return
  }
  intervalId = setInterval(() => {
    currentImageIndex.value = (currentImageIndex.value + 1) % 5
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
  padding-bottom: 46%; /* 315/685 */
}

.relative.overflow-hidden img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.gradient-sweep {
  background: linear-gradient(90deg, #f97316 0%, #fb923c 50%, #f97316 100%);
  background-size: 200% 100%;
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  animation: sweep 6s ease-in-out infinite;
}
@keyframes sweep {
  0%, 100% { background-position: 0% 50%; }
  50%      { background-position: 100% 50%; }
}
</style>
