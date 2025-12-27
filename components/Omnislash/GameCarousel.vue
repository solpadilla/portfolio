<template>
  <div id="fixed-content">
    <!-- CAROUSEL -->
    <div id="carousel">
      <img v-for="game in games" :key="game" :src="game.src" :alt="game.name" data-not-lazy />
      <img v-for="game in games" :key="game" :src="game.src" :alt="game.name" data-not-lazy />
      <img v-for="game in games.slice(0, 4)" :key="game" :src="game.src" :alt="game.name" data-not-lazy />
    </div>
    <!-- CAROUSEL -->
  </div>
</template>

<script setup>
  const games = [
    {"name":"Marvel Snap","src":"/omni/banner/marvelsnap.jpg"},
    {"name":"Chess","src":"/omni/banner/chess.jpg"},
    {"name":"Counter-Strike 2","src":"/omni/banner/csgo.jpg"},
    {"name":"Dota 2","src":"/omni/banner/dota2.jpg"},
    {"name":"Fall Guys","src":"/omni/banner/fallguys.jpg"},
    {"name":"Fortnite","src":"/omni/banner/fortnite.jpg"},
    {"name":"Hearthstone","src":"/omni/banner/hearthstone.jpg"},
    {"name":"League of Legends","src":"/omni/banner/lol.jpg"},
    {"name":"Legends of Runeterra","src":"/omni/banner/lor.jpg"},
    {"name":"TFT","src":"/omni/banner/tft.jpg"}
  ];
</script>

<style scoped lang="scss">
#fixed-content {
  position: fixed;
  display: flex;
  flex-direction: column;
  gap: 64px;
  margin-top: 85px;
  #carousel {
    display: flex;
    gap: 16px;
    animation: scroll 120s linear infinite;
    opacity: 0.5;
    img {
      border-radius: 20px;
      width: 752px;
      height: 225px;
      object-fit: cover;
    }
  }
}

@keyframes scroll {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(calc(-768px * 10));
  }
}
</style>