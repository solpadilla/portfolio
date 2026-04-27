<template>
  <h2 class="text-[32px] my-4 font-sans font-bold">
    <nuxt-link class="flex items-center justify-center gap-1" to="https://emotesizer.com" target="_blank" rel="noopener noreferrer">
      Emote<span class="bg-gradient-to-r from-[#3B82F6] to-[#14B8A6] bg-clip-text text-transparent">Sizer</span>
    </nuxt-link>
  </h2>

  <!-- Interactive Showcase Container (always dark) -->
  <nuxt-link
    to="https://emotesizer.com"
    target="_blank"
    rel="noopener noreferrer"
    aria-label="Visit Emotesizer — open emotesizer.com in a new tab"
    class="block cursor-pointer bg-[#0d0d0d] border border-[#2a2a2a] rounded-xl overflow-hidden p-4 sm:p-5 md:p-6 w-full max-w-[685px]"
  >
    <div aria-hidden="true" class="flex flex-col gap-4">

      <!-- Mini Header Bar -->
      <div class="flex items-center justify-between pb-3 border-b border-[#2a2a2a]">
        <span class="font-sans text-sm font-bold uppercase tracking-widest">
          <span class="text-[#f0f0f0]">EMOTE</span><span class="bg-gradient-to-r from-[#3B82F6] to-[#14B8A6] bg-clip-text text-transparent">SIZER</span>
        </span>
        <div class="flex items-center gap-2">
          <span class="relative flex h-1.5 w-1.5">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-[#14B8A6] opacity-60"></span>
            <span class="relative inline-flex rounded-full h-1.5 w-1.5 bg-[#14B8A6]"></span>
          </span>
          <!-- Mobile (<sm): compact label. sm+: full pill with monospaced accent -->
          <span class="text-[10px] text-[#666] sm:hidden">Browser-based</span>
          <span class="text-[10px] text-[#666] hidden sm:inline">100% <span class="text-[#a0a0a0] font-mono">in-browser</span></span>
        </div>
      </div>

      <!-- Stage Area: Source -> (chevrons + ring) -> Output -->
      <div class="grid grid-cols-1 sm:grid-cols-[1fr_auto_1fr] items-center gap-4">

        <!-- Source Panel -->
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] p-4 flex flex-col items-center">
          <div class="text-[9px] font-semibold uppercase tracking-widest text-[rgba(255,255,255,0.4)] mb-2">Source</div>
          <div class="es-checker w-32 h-32 rounded flex items-center justify-center">
            <svg viewBox="0 0 100 100" width="80" height="80" aria-hidden="true">
              <circle cx="50" cy="50" r="44" fill="#facc15" />
              <circle cx="36" cy="42" r="5" fill="#0d0d0d" />
              <circle cx="64" cy="42" r="5" fill="#0d0d0d" />
              <path
                class="es-mouth"
                d="M 32 62 Q 50 78 68 62"
                fill="none"
                stroke="#0d0d0d"
                stroke-width="5"
                stroke-linecap="round"
                style="transform-origin: 50px 62px;"
              />
            </svg>
          </div>
          <div class="text-[10px] font-mono text-[rgba(255,255,255,0.5)] mt-2">source.gif &middot; 512&times;512</div>
        </div>

        <!-- Middle Column: chevrons (sm+), ring + divider (mobile) -->
        <div class="flex flex-col items-center gap-2">
          <!-- Horizontal chevrons (sm+) -->
          <div class="hidden sm:flex items-center gap-1">
            <Icon name="mdi:chevron-right" size="18" class="es-chevron es-chevron-1 text-[#3B82F6]" />
            <Icon name="mdi:chevron-right" size="18" class="es-chevron es-chevron-2 text-[#3B82F6]" />
            <Icon name="mdi:chevron-right" size="18" class="es-chevron es-chevron-3 text-[#3B82F6]" />
          </div>
          <!-- Mobile divider (<sm) -->
          <div class="sm:hidden h-px w-12 bg-[rgba(255,255,255,0.1)]"></div>

          <!-- Progress ring -->
          <div class="relative" aria-hidden="true">
            <svg width="44" height="44" viewBox="0 0 44 44">
              <defs>
                <linearGradient id="es-ring-grad" x1="0%" y1="0%" x2="100%" y2="100%">
                  <stop offset="0%" stop-color="#3B82F6" />
                  <stop offset="100%" stop-color="#14B8A6" />
                </linearGradient>
              </defs>
              <!-- Track -->
              <circle cx="22" cy="22" r="18" fill="none" stroke="#1f2937" stroke-width="3" />
              <!-- Fill (sweeps 0 -> 100% via stroke-dashoffset animation) -->
              <circle
                class="es-ring-fill"
                cx="22"
                cy="22"
                r="18"
                fill="none"
                stroke="url(#es-ring-grad)"
                stroke-width="3"
                stroke-linecap="round"
                stroke-dasharray="113.097"
                stroke-dashoffset="113.097"
                transform="rotate(-90 22 22)"
                :key="stepIndex"
              />
            </svg>
            <span class="absolute inset-0 flex items-center justify-center text-[8px] font-mono font-bold tabular-nums text-[#f0f0f0]">100%</span>
          </div>
        </div>

        <!-- Output Panel -->
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] p-4 flex flex-col items-center">
          <div class="text-[9px] font-semibold uppercase tracking-widest text-[rgba(255,255,255,0.4)] mb-2">Output</div>
          <div class="min-h-[140px] flex items-center justify-center">
            <div
              class="es-output-tile es-checker rounded flex items-center justify-center"
              :style="{ width: outputSize + 'px', height: outputSize + 'px' }"
            >
              <svg viewBox="0 0 100 100" width="100%" height="100%" aria-hidden="true">
                <circle cx="50" cy="50" r="44" fill="#facc15" />
                <circle cx="36" cy="42" r="5" fill="#0d0d0d" />
                <circle cx="64" cy="42" r="5" fill="#0d0d0d" />
                <path
                  class="es-mouth"
                  d="M 32 62 Q 50 78 68 62"
                  fill="none"
                  stroke="#0d0d0d"
                  stroke-width="5"
                  stroke-linecap="round"
                  style="transform-origin: 50px 62px;"
                />
              </svg>
            </div>
          </div>
          <div class="text-[10px] font-mono text-[#14B8A6] mt-2 tabular-nums">{{ outputCaption }}</div>
        </div>
      </div>

      <!-- Metrics Row -->
      <div class="grid grid-cols-3 gap-2 mt-1">
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] p-2">
          <div class="text-[8px] uppercase tracking-widest text-[rgba(255,255,255,0.4)]">File Size</div>
          <div class="text-base font-mono font-bold tabular-nums text-[#22c55e]">{{ fileSize }}</div>
        </div>
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] p-2">
          <div class="text-[8px] uppercase tracking-widest text-[rgba(255,255,255,0.4)]">Dimensions</div>
          <div class="text-base font-mono font-bold tabular-nums text-[#f0f0f0]">{{ dimensionsLabel }}</div>
        </div>
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] p-2">
          <div class="text-[8px] uppercase tracking-widest text-[rgba(255,255,255,0.4)]">Format</div>
          <div class="flex items-center gap-1 mt-0.5">
            <span class="px-1.5 py-0.5 rounded text-[10px] font-mono bg-[rgba(255,255,255,0.06)] text-[rgba(255,255,255,0.6)]">GIF</span>
            <Icon name="mdi:arrow-right" class="text-[rgba(255,255,255,0.4)]" size="12" />
            <span class="px-1.5 py-0.5 rounded text-[10px] font-mono bg-[#14B8A6]/15 text-[#14B8A6]">GIF</span>
          </div>
        </div>
      </div>

      <!-- Platform Pills Row -->
      <div aria-hidden="true" class="flex flex-wrap gap-2 mt-1 justify-center">
        <span
          v-for="platform in platforms"
          :key="platform.id"
          class="inline-flex items-center gap-1.5 px-2.5 py-1 rounded-full text-[10px] font-semibold border transition-all duration-300"
          :class="[platform.inactive, activePlatform === platform.id ? platform.active : '']"
        >
          <Icon :name="platform.icon" size="10" />
          {{ platform.name }}
          <Icon v-if="activePlatform === platform.id" name="mdi:check" size="10" />
        </span>
      </div>

    </div>
  </nuxt-link>

  <p class="text-center mt-6 max-w-xl">A free, browser-based emote maker for Twitch, Discord, Kick, 7TV, BTTV, and FFZ — search GIFs, then resize, crop, and compress them into platform-ready emotes without ever uploading a file.</p>

  <div class="flex flex-col items-center my-3">
    <strong>Built with:</strong>
    <ul class="flex flex-wrap gap-2 text-center justify-center">
      <li><Icon name="simple-icons:anthropic" /> Claude AI,</li>
      <li><Icon name="logos:nuxt-icon" /> Nuxt 3,</li>
      <li><Icon name="devicon:vuejs" /> Vue 3,</li>
      <li><Icon name="devicon:typescript" /> TypeScript,</li>
      <li><Icon name="devicon:tailwindcss" /> Tailwind CSS,</li>
      <li><Icon name="logos:pinia" /> Pinia,</li>
      <li><Icon name="simple-icons:ffmpeg" /> FFmpeg.wasm,</li>
      <li><Icon name="simple-icons:webassembly" /> WebAssembly</li>
    </ul>
  </div>

  <div class="flex mt-4 gap-10">
    <nuxt-link to="https://emotesizer.com" target="_blank" rel="noopener noreferrer">
      <UIButton>View Live</UIButton>
    </nuxt-link>
    <nuxt-link to="https://github.com/solpadilla/emotesizer" target="_blank" rel="noopener noreferrer">
      <UIButton>View Code</UIButton>
    </nuxt-link>
  </div>
</template>

<script setup>
// Single source-of-truth lookup table for the demo cycle.
// Each step represents one platform-target export pass: shrink (or resize) the
// emote to the target's required dimensions and report the resulting file size.
const steps = [
  { size: 112, fileSize: '487 KB', dimensions: '112×112', caption: 'Twitch 112×112',  platform: 'twitch' },
  { size: 56,  fileSize: '168 KB', dimensions: '56×56',   caption: 'Discord 56×56',   platform: 'discord' },
  { size: 28,  fileSize: '91 KB',  dimensions: '28×28',   caption: 'Kick 28×28',      platform: 'kick' },
  { size: 128, fileSize: '312 KB', dimensions: '128×128', caption: '7TV 128×128',     platform: '7tv' },
]

// `simple-icons:7tv` is not reliably present in the Iconify registry, so we fall
// back to `mdi:flash` — a neutral lightning bolt that visually matches 7TV's vibe.
const platforms = [
  {
    id: 'twitch',
    name: 'Twitch',
    icon: 'fa-brands:twitch',
    inactive: 'border-[#9146FF]/40 text-[#9146FF]',
    active: 'bg-[#9146FF]/15 shadow-[0_0_12px_rgba(145,70,255,0.4)]',
  },
  {
    id: 'discord',
    name: 'Discord',
    icon: 'fa-brands:discord',
    inactive: 'border-[#5865F2]/40 text-[#5865F2]',
    active: 'bg-[#5865F2]/15 shadow-[0_0_12px_rgba(88,101,242,0.4)]',
  },
  {
    id: 'kick',
    name: 'Kick',
    icon: 'simple-icons:kick',
    inactive: 'border-[#53FC18]/40 text-[#53FC18]',
    active: 'bg-[#53FC18]/15 shadow-[0_0_12px_rgba(83,252,24,0.4)]',
  },
  {
    id: '7tv',
    name: '7TV',
    icon: 'mdi:flash',
    inactive: 'border-[#1F69FF]/40 text-[#1F69FF]',
    active: 'bg-[#1F69FF]/15 shadow-[0_0_12px_rgba(31,105,255,0.4)]',
  },
]

const stepIndex = ref(0)
let cycleTimer = null

// Derived values are pulled from the single steps[] table to keep the demo
// frozen-in-sync if any one piece of state were ever to lag behind.
const currentStep    = computed(() => steps[stepIndex.value])
const outputSize     = computed(() => currentStep.value.size)
const fileSize       = computed(() => currentStep.value.fileSize)
const dimensionsLabel = computed(() => currentStep.value.dimensions)
const outputCaption  = computed(() => currentStep.value.caption)
const activePlatform = computed(() => currentStep.value.platform)

function startCycle() {
  cycleTimer = setInterval(() => {
    stepIndex.value = (stepIndex.value + 1) % steps.length
  }, 1600)
}

function cleanup() {
  if (cycleTimer) {
    clearInterval(cycleTimer)
    cycleTimer = null
  }
}

onMounted(() => {
  // Honor user's reduced-motion preference: freeze on Twitch 112×112.
  // `window` is implicitly client-only inside onMounted, but the typeof guard
  // keeps the component safe under any future SSR-time invocation.
  if (typeof window !== 'undefined') {
    const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches
    if (prefersReducedMotion) return
  }
  startCycle()
})

onBeforeUnmount(() => {
  cleanup()
})
</script>

<style scoped>
/* Checkerboard tile background — pure CSS, no asset dependencies. */
.es-checker {
  background-image:
    linear-gradient(45deg, #1a1a1a 25%, transparent 25%),
    linear-gradient(-45deg, #1a1a1a 25%, transparent 25%),
    linear-gradient(45deg, transparent 75%, #1a1a1a 75%),
    linear-gradient(-45deg, transparent 75%, #1a1a1a 75%);
  background-size: 16px 16px;
  background-position: 0 0, 0 8px, 8px -8px, -8px 0px;
  background-color: #222;
}

/* Output tile size transitions on stepIndex change to visually "shrink" the emote. */
.es-output-tile {
  transition: width 600ms ease, height 600ms ease;
  box-shadow:
    0 0 24px rgba(59, 130, 246, 0.35),
    0 0 48px rgba(20, 184, 166, 0.2);
}

/* Emote face mouth: alternates between smile and a wider "o" shape. */
@keyframes es-mouth-bounce {
  0%, 100% { transform: scaleY(1); }
  50%      { transform: scaleY(1.6); }
}
.es-mouth {
  animation: es-mouth-bounce 1.4s ease-in-out infinite alternate;
}

/* Chevron cycling: each chevron pulses opacity left-to-right on a 1.2s loop. */
@keyframes es-chevron-pulse {
  0%, 100% { opacity: 0.25; }
  50%      { opacity: 1; }
}
.es-chevron {
  animation: es-chevron-pulse 1.2s ease-in-out infinite;
}
.es-chevron-1 { animation-delay: 0s; }
.es-chevron-2 { animation-delay: 0.2s; }
.es-chevron-3 { animation-delay: 0.4s; }

/* Progress ring fill: sweeps 0 -> 100% over 1.6s (matches step interval).
   Re-keying the circle on stepIndex change restarts the animation each beat. */
@keyframes es-ring-sweep {
  from { stroke-dashoffset: 113.097; }
  to   { stroke-dashoffset: 0; }
}
.es-ring-fill {
  animation: es-ring-sweep 1.6s ease-out forwards;
}

/* Reduced-motion guard — freeze every visual rhythm in the showcase. */
@media (prefers-reduced-motion: reduce) {
  .es-mouth,
  .es-chevron,
  .es-ring-fill {
    animation: none !important;
  }
  .es-output-tile {
    transition: none !important;
  }
}
</style>
