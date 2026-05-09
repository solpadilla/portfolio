<template>
  <h2 class="text-[32px] my-4 font-raj font-bold uppercase tracking-[0.02em]">
    <nuxt-link class="flex items-center justify-center gap-1" to="https://halorecord.com" target="_blank" rel="noopener noreferrer">
      Halo <span class="accent">Record</span>
    </nuxt-link>
  </h2>

  <nuxt-link
    to="https://halorecord.com"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Open halorecord.com in a new tab"
    class="block w-full max-w-[685px] mx-auto bg-[#0d0d0d] border border-[#2a2a2a] rounded-xl overflow-hidden cursor-pointer"
  >
    <div class="relative w-full aspect-video max-h-[50svh] bg-[#060606]">
      <video
        src="/halorecord/halorecord.mp4"
        autoplay
        muted
        loop
        playsinline
        preload="metadata"
        aria-label="Halo Record dashboard preview — looping screen capture"
        class="absolute inset-0 w-full h-full object-cover"
      ></video>
    </div>
  </nuxt-link>

  <p class="text-center mt-6 max-w-xl">A Halo MCC player statistics platform featuring TrueSkill ratings, service records, match history with carnage reports, and season leaderboards.</p>

  <div class="flex flex-col items-center my-3">
    <strong>Built with:</strong>
    <ul class="flex flex-wrap gap-2 text-center justify-center">
      <li><Icon name="simple-icons:anthropic" /> Claude AI,</li>
      <li><Icon name="logos:nuxt-icon" /> Nuxt 3,</li>
      <li><Icon name="devicon:vuejs" /> Vue 3,</li>
      <li><Icon name="devicon:typescript" /> TypeScript,</li>
      <li><Icon name="devicon:tailwindcss" /> Tailwind CSS,</li>
      <li><Icon name="devicon:prisma" /> Prisma,</li>
      <li><Icon name="devicon:postgresql" /> PostgreSQL</li>
    </ul>
  </div>

  <div class="flex mt-4 gap-10">
    <nuxt-link to="https://halorecord.com" target="_blank" rel="noopener noreferrer">
      <UIButton>View Live</UIButton>
    </nuxt-link>
  </div>
</template>

<style scoped>
.accent {
  color: #ff5560;
  text-shadow:
    0 0 36px rgba(255, 60, 80, 0.6),
    0 0 12px rgba(255, 60, 80, 0.5);
  animation: breathe 6s ease-in-out infinite;
}

@keyframes breathe {
  0%, 100% {
    text-shadow:
      0 0 36px rgba(255, 60, 80, 0.55),
      0 0 12px rgba(255, 60, 80, 0.45);
  }
  50% {
    text-shadow:
      0 0 56px rgba(255, 60, 80, 0.85),
      0 0 20px rgba(255, 60, 80, 0.7),
      0 0 4px rgba(255, 220, 220, 0.3);
  }
}

@media (prefers-reduced-motion: reduce) {
  .accent {
    animation: none;
  }
}
</style>
