<template>
  <h2 class="text-[32px] my-4 font-sans font-bold">
    <nuxt-link class="flex items-center justify-center gap-1" to="https://halorecord.com" target="_blank" rel="noopener noreferrer">
      Halo <span class="text-[#00d4ff]">Record</span>
    </nuxt-link>
  </h2>

  <!-- Interactive Showcase Container (always dark) -->
  <nuxt-link to="https://halorecord.com" target="_blank" rel="noopener noreferrer" aria-hidden="true" class="block cursor-pointer bg-[#0d0d0d] border border-[#2a2a2a] rounded-xl overflow-hidden p-5 md:p-6 w-full max-w-[685px]">
    <div class="flex flex-col gap-4">

      <!-- Mini Header Bar -->
      <div class="flex items-center justify-between pb-3 border-b border-[#2a2a2a]">
        <span class="font-raj text-sm font-bold uppercase tracking-widest">
          <span class="text-[#f0f0f0]">HALO</span><span class="text-[#00d4ff]"> RECORD</span>
        </span>
        <div class="flex items-center gap-2">
          <span class="relative flex h-1.5 w-1.5">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-[#00d4ff] opacity-60"></span>
            <span class="relative inline-flex rounded-full h-1.5 w-1.5 bg-[#00d4ff]"></span>
          </span>
          <span class="text-[10px] text-[#666]"><span class="text-[#a0a0a0] font-mono">12,847</span> tracked players</span>
        </div>
      </div>

      <!-- Mini Search Bar -->
      <div class="mt-3">
        <div class="flex">
          <div class="flex-1 h-10 rounded-l-lg bg-[rgba(255,255,255,0.06)] border border-[rgba(255,255,255,0.10)] relative flex items-center">
            <span class="absolute left-3 text-[rgba(255,255,255,0.3)]">
              <Icon name="fa-solid:search" size="12" />
            </span>
            <span class="text-[#f0f0f0] text-sm font-raj pl-9 pr-3">{{ displayedText }}<span class="cursor-blink">|</span></span>
          </div>
          <div class="h-10 px-5 rounded-r-lg bg-[#00d4ff] flex items-center justify-center" role="button" aria-label="Search">
            <Icon name="fa-solid:search" size="14" class="text-[#0d0d0d]" />
          </div>
        </div>
        <div class="mt-2 flex items-center justify-center gap-x-2">
          <span class="text-[10px] text-[rgba(255,255,255,0.35)]">Try:</span>
          <span class="text-[10px] text-[rgba(255,255,255,0.5)]">Tylenul</span>
          <span class="text-[10px] text-[rgba(255,255,255,0.25)]">/</span>
          <span class="text-[10px] text-[rgba(255,255,255,0.5)]">Colin Rages</span>
          <span class="text-[10px] text-[rgba(255,255,255,0.25)]">/</span>
          <span class="text-[10px] text-[rgba(255,255,255,0.5)]">Gory Figment</span>
        </div>
      </div>

      <!-- Mini Stats Dashboard -->
      <div class="grid grid-cols-1 sm:grid-cols-2 gap-3 mt-3">

        <!-- Left: Mini Leaderboard -->
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] p-3">
          <div class="flex items-center gap-2 mb-2">
            <div class="w-0.5 h-4 bg-[#00d4ff] rounded-full"></div>
            <span class="text-[11px] font-raj font-semibold uppercase tracking-wider text-[#f0f0f0]">Leaderboard</span>
          </div>
          <div class="flex items-center gap-1 mb-2">
            <span class="text-[9px] font-semibold uppercase tracking-wider px-2 py-1 text-[#00d4ff] border-b border-[#00d4ff]">Kills</span>
            <span class="text-[9px] font-semibold uppercase tracking-wider px-2 py-1 text-[rgba(255,255,255,0.35)]">K/D</span>
            <span class="text-[9px] font-semibold uppercase tracking-wider px-2 py-1 text-[rgba(255,255,255,0.35)]">Wins</span>
          </div>
          <div class="flex flex-col gap-1.5">
            <div v-for="(entry, i) in leaderboardData" :key="i" class="flex items-center gap-2">
              <span class="text-[10px] font-mono font-bold w-4 text-center" :class="rankColor(i)">{{ i + 1 }}</span>
              <span class="text-[10px] font-raj font-bold tracking-wider flex-1 truncate text-[rgba(255,255,255,0.8)]">{{ entry.name }}</span>
              <span class="text-[10px] font-mono font-semibold tabular-nums text-[rgba(255,255,255,0.5)]">{{ entry.kills }}</span>
            </div>
          </div>
        </div>

        <!-- Right: Mini Player Stats Card -->
        <div class="bg-[#060303] rounded-lg border border-[rgba(255,255,255,0.06)] border-l-2 border-l-[#00d4ff] p-3">
          <div class="mb-1">
            <div class="text-sm font-raj font-bold tracking-wider text-[#f0f0f0]">Tylenul</div>
            <div class="text-[9px] text-[rgba(0,212,255,0.6)] font-medium tracking-wide uppercase">General</div>
          </div>
          <div class="grid grid-cols-2 gap-2 mt-2">
            <div>
              <div class="text-base font-mono font-bold tabular-nums text-[#00ff66]">2.33</div>
              <div class="text-[8px] font-medium uppercase tracking-widest text-[rgba(255,255,255,0.4)] mt-0.5">K/D</div>
            </div>
            <div>
              <div class="text-base font-mono font-bold tabular-nums text-[#00ff66]">68.4%</div>
              <div class="text-[8px] font-medium uppercase tracking-widest text-[rgba(255,255,255,0.4)] mt-0.5">Win Rate</div>
            </div>
            <div>
              <div class="text-base font-mono font-bold tabular-nums text-[#f0f0f0]">284,912</div>
              <div class="text-[8px] font-medium uppercase tracking-widest text-[rgba(255,255,255,0.4)] mt-0.5">Kills</div>
            </div>
            <div>
              <div class="text-base font-mono font-bold tabular-nums text-[#f0f0f0]">4,218</div>
              <div class="text-[8px] font-medium uppercase tracking-widest text-[rgba(255,255,255,0.4)] mt-0.5">Games</div>
            </div>
          </div>
          <div class="mt-3 pt-2 border-t border-[rgba(255,255,255,0.06)] flex items-center justify-between">
            <span class="text-[9px] uppercase tracking-wider text-[rgba(0,212,255,0.5)]">Top Rating</span>
            <span class="text-[11px] font-mono font-bold text-[#00d4ff]">#12</span>
          </div>
        </div>

      </div>
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

<script setup>
const gamertags = ['Tylenul', 'Colin Rages', 'Gory Figment']
const displayedText = ref('')
let currentTagIndex = 0
let currentCharIndex = 0
let typingTimer = null
let phaseTimer = null

// Decorative demo data for portfolio showcase
const leaderboardData = [
  { name: 'Tylenul', kills: '284,912' },
  { name: 'Colin Rages', kills: '201,447' },
  { name: 'Gory Figment', kills: '178,293' },
  { name: 'WyvernSlayer', kills: '156,820' },
  { name: 'GhostRecon117', kills: '143,558' },
]

function rankColor(index) {
  if (index === 0) return 'text-[#ffd700]'
  if (index === 1) return 'text-[#c0c0c0]'
  if (index === 2) return 'text-[#cd7f32]'
  return 'text-[rgba(255,255,255,0.35)]'
}

function startTyping() {
  const tag = gamertags[currentTagIndex]
  typingTimer = setInterval(() => {
    if (currentCharIndex < tag.length) {
      displayedText.value = tag.slice(0, currentCharIndex + 1)
      currentCharIndex++
    } else {
      clearInterval(typingTimer)
      typingTimer = null
      // Pause after completing a gamertag
      phaseTimer = setTimeout(() => {
        // Clear instantly
        displayedText.value = ''
        currentCharIndex = 0
        currentTagIndex = (currentTagIndex + 1) % gamertags.length
        // Wait then start next
        phaseTimer = setTimeout(() => {
          startTyping()
        }, 500)
      }, 2000)
    }
  }, 100)
}

function cleanup() {
  if (typingTimer) {
    clearInterval(typingTimer)
    typingTimer = null
  }
  if (phaseTimer) {
    clearTimeout(phaseTimer)
    phaseTimer = null
  }
}

onMounted(() => {
  startTyping()
})

onBeforeUnmount(() => {
  cleanup()
})
</script>

<style scoped>
@keyframes blink-cursor {
  0%, 100% { opacity: 1; }
  50% { opacity: 0; }
}
.cursor-blink {
  animation: blink-cursor 1.06s step-end infinite;
  color: #00d4ff;
}
</style>
