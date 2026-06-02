<template>
  <h2 class="text-[32px] my-4 font-sans font-bold">
    <nuxt-link class="flex items-center justify-center" to="https://legitski.com" target="_blank" rel="noopener noreferrer">
      <span class="legitski-wordmark">Legitski</span>
    </nuxt-link>
  </h2>

  <!-- Showcase: real product screenshot, framed like the HaloRecord media card -->
  <nuxt-link
    to="https://legitski.com"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Visit Legitski — open legitski.com in a new tab"
    class="block w-full max-w-[685px] mx-auto bg-[#0d0d0d] border border-[#2a2a2a] rounded-xl overflow-hidden cursor-pointer"
  >
    <div class="relative w-full aspect-[1920/925] bg-[#060606]">
      <img
        src="/legitski/legitski-landing.png"
        alt="Legitski landing page — multi-tenant inventory management platform"
        loading="eager"
        decoding="async"
        data-not-lazy
        class="absolute inset-0 w-full h-full object-cover object-top"
      />
    </div>
  </nuxt-link>

  <p class="text-center mt-6 max-w-xl">A multi-tenant inventory platform where teams define their own item schema, scan barcodes, and track stock in real time — with low-stock alerts, Excel/PDF exports, Stripe billing, and native iOS/Android apps from one PWA-ready codebase.</p>

  <div class="flex flex-col items-center my-3">
    <strong>Built with:</strong>
    <ul class="flex flex-wrap gap-2 text-center justify-center">
      <li><Icon name="simple-icons:anthropic" /> Claude AI,</li>
      <li><Icon name="logos:nuxt-icon" /> Nuxt 3,</li>
      <li><Icon name="devicon:vuejs" /> Vue 3,</li>
      <li><Icon name="devicon:typescript" /> TypeScript,</li>
      <li><Icon name="devicon:tailwindcss" /> Tailwind CSS,</li>
      <li><Icon name="logos:pinia" /> Pinia,</li>
      <li><Icon name="logos:prisma" /> Prisma,</li>
      <li><Icon name="logos:postgresql" /> PostgreSQL,</li>
      <li><Icon name="logos:socket-io" /> Socket.io,</li>
      <li><Icon name="logos:stripe" /> Stripe,</li>
      <li><Icon name="simple-icons:capacitor" /> Capacitor,</li>
      <li><Icon name="simple-icons:pwa" /> PWA</li>
    </ul>
  </div>

  <div class="flex mt-4 justify-center">
    <nuxt-link to="https://legitski.com" target="_blank" rel="noopener noreferrer">
      <UIButton>View Live</UIButton>
    </nuxt-link>
  </div>
</template>

<style scoped>
/* Brand wordmark: render "Legitski" as plain white text. */
.legitski-wordmark {
  color: #ffffff;
  letter-spacing: -0.02em;
}
</style>
