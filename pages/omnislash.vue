<template>
  <div>
    <!-- Nav Bar -->
    <nav class="flex justify-between bg-[rgba(26,29,32,0.75)] backdrop-blur-sm position-fixed w-full z-10 px-4 text-white">
      <a href="https://web.archive.org/web/20250709091739/https://omnislash.com/">
        <img src="/omni/omni-logo.svg" alt="Omnislash Logo" data-not-lazy />
      </a>
    </nav>
    <!-- Nav Bar -->

    <main>
      <OmnislashLandingBG top="430" />
      <OmnislashGameCarousel />

      <section>
        <div id="app-desc">
          <header>
            <img src="/omni/omni-gif.gif" alt="Omnislash" data-not-lazy />
          </header>
          <b>Record, store and share your game play</b>
          <p>
            Gameplay to GIF in minutes, omnislash turns your best (and quirky) gaming moments into shareable clips, GIFs, stats and more.
          </p>
          <footer>
            <button class="primary-btn blue-theme">
              <Icon name="ri:windows-fill" />
              &nbsp;&nbsp;Download<span> the FREE windows app</span>
            </button>
            <img src="/omni/rgb-slash.svg" alt="Omnislash RGB Slash" />
          </footer>
        </div>
      </section>

      <section id="contact">
        <a href="https://discord.com/invite/QZa5xw8?utm_campaign=discord_landing_page_link&utm_medium=web&utm_source=landingpage" target="_blank" class="reg-link no-decoration">
          <button class="primary-btn discord-theme">
            <div class="svg-wrapper">
              <svg xmlns="http://www.w3.org/2000/svg" width="54" height="42" viewBox="0 0 54 42" fill="none">
                <g clip-path="url(#clip0_1321_93858)">
                <path d="M45.5514 4.09881C45.5369 4.06979 45.5124 4.04802 45.4825 4.03532C42.024 2.44893 38.375 1.31696 34.6262 0.669337C34.5564 0.656638 34.4856 0.689291 34.4521 0.751876C33.955 1.65346 33.5042 2.58045 33.1006 3.52739C29.0598 2.91423 24.9491 2.91423 20.9074 3.52739C20.5011 2.57773 20.043 1.65074 19.5351 0.751876C19.4997 0.691105 19.4299 0.658452 19.3609 0.669337C15.6113 1.31605 11.9623 2.44711 8.50469 4.03532C8.47476 4.04802 8.45027 4.06888 8.43303 4.097C1.51875 14.4217 -0.375131 24.4934 0.553667 34.4399C0.55911 34.4888 0.583599 34.5342 0.622602 34.565C4.64891 37.5464 9.15231 39.8213 13.9405 41.2943C14.0095 41.3151 14.0838 41.2906 14.1274 41.2326C15.1559 39.8331 16.0666 38.3519 16.8521 36.8027C16.8938 36.7192 16.8612 36.6176 16.7777 36.5759C16.7714 36.5732 16.7659 36.5705 16.7596 36.5677C15.3228 36.0181 13.9314 35.355 12.599 34.5859C12.5174 34.5378 12.4902 34.4335 12.5382 34.3519C12.5491 34.3328 12.5646 34.3156 12.5818 34.302C12.8611 34.0925 13.1414 33.8748 13.4081 33.6544C13.4562 33.6145 13.5233 33.6054 13.5804 33.6308C22.3088 37.6145 31.7582 37.6145 40.3831 33.6308C40.4403 33.6036 40.5083 33.6117 40.5573 33.6516C40.824 33.8721 41.1042 34.0916 41.3854 34.3011C41.4607 34.3573 41.4761 34.4643 41.4199 34.5405C41.4063 34.5587 41.3899 34.5732 41.3709 34.585C40.0421 35.3614 38.6489 36.0235 37.2085 36.565C37.1206 36.5986 37.077 36.6965 37.1097 36.7845C37.1115 36.7909 37.1142 36.7963 37.1178 36.8018C37.916 38.3419 38.8258 39.8222 39.8398 41.2299C39.8825 41.2888 39.9578 41.3142 40.0267 41.2934C44.8231 39.8258 49.3346 37.5501 53.3655 34.5641C53.4054 34.5351 53.4308 34.4907 53.4353 34.4417C54.5473 22.9424 51.5732 12.9532 45.5505 4.09791L45.5514 4.09881ZM18.1555 28.3836C15.5278 28.3836 13.3627 25.9718 13.3627 23.0104C13.3627 20.0489 15.4861 17.6371 18.1555 17.6371C20.8249 17.6371 22.9909 20.0698 22.9482 23.0104C22.9482 25.9718 20.8249 28.3836 18.1555 28.3836ZM35.877 28.3836C33.2494 28.3836 31.0843 25.9718 31.0843 23.0104C31.0843 20.0489 33.2076 17.6371 35.877 17.6371C38.5464 17.6371 40.7124 20.0698 40.6698 23.0104C40.6698 25.9718 38.5673 28.3836 35.877 28.3836Z" fill="white" fill-opacity="0.87"/>
                </g>
                <defs>
                <clipPath id="clip0_1321_93858">
                <rect width="53.3333" height="40.6349" fill="white" transform="translate(0.333344 0.666626)"/>
                </clipPath>
                </defs>
              </svg>
              <transition name="bounce">
                <svg class="discord-bubble" xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 48 48" fill="none">
                  <path d="M5.61699 41.8276C5.62521 41.8189 5.63457 41.809 5.64503 41.7978C5.63592 41.8079 5.62663 41.8179 5.61716 41.8278L5.61699 41.8276ZM2.75766 39.0311L2.74195 39.0468L2.72659 39.0629C1.98693 39.8362 1.80488 40.9632 2.21958 41.9202C2.64079 42.8923 3.58469 43.5 4.625 43.5C9.71213 43.5 13.6497 41.374 15.9577 39.726C18.4489 40.5401 21.1582 41 24 41C35.7433 41 46 33.1992 46 22.75C46 12.3008 35.7433 4.5 24 4.5C12.2567 4.5 2 12.3008 2 22.75C2 26.8128 3.59454 30.5112 6.20311 33.4825C5.73357 34.7701 5.01361 36.0113 4.31214 37.033C3.56579 38.1201 2.91341 38.8544 2.7783 39.0065C2.75428 39.0335 2.74661 39.0421 2.75766 39.0311Z" fill="white" fill-opacity="0.87" stroke="#455383" stroke-width="4"/>
                </svg>
              </transition>
            </div>
            <div>
              <b>Join us on Discord!</b>
              <p>Share feedback, get tech support or show off your clips.</p>
            </div>
          </button>
        </a>

        <p>No Discord? No problem. Email us at: <a href="mailto:sayhello@omnislash.com" class="reg-link email-link no-decoration"><Icon name="tabler:mail-filled" />&nbsp;sayhello@omnislash.com</a></p>
      </section>

      <section>
        <label>/how it works</label>
        <ul>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="65" height="65" viewBox="0 0 65 65" fill="none">
              <path d="M28.3334 5.99487H36.6667C38.0521 5.99487 39.1667 7.10946 39.1667 8.49487V25.9949H48.3021C50.1563 25.9949 51.0834 28.2345 49.7709 29.547L33.9271 45.4011C33.1459 46.1824 31.8646 46.1824 31.0834 45.4011L15.2188 29.547C13.9063 28.2345 14.8334 25.9949 16.6875 25.9949H25.8334V8.49487C25.8334 7.10946 26.948 5.99487 28.3334 5.99487ZM59.1667 45.1615V56.8282C59.1667 58.2136 58.0521 59.3282 56.6667 59.3282H8.33337C6.94796 59.3282 5.83337 58.2136 5.83337 56.8282V45.1615C5.83337 43.7761 6.94796 42.6615 8.33337 42.6615H23.6146L28.7188 47.7657C30.8125 49.8595 34.1875 49.8595 36.2813 47.7657L41.3855 42.6615H56.6667C58.0521 42.6615 59.1667 43.7761 59.1667 45.1615ZM46.25 54.3282C46.25 53.1824 45.3125 52.2449 44.1667 52.2449C43.0209 52.2449 42.0834 53.1824 42.0834 54.3282C42.0834 55.474 43.0209 56.4115 44.1667 56.4115C45.3125 56.4115 46.25 55.474 46.25 54.3282ZM52.9167 54.3282C52.9167 53.1824 51.9792 52.2449 50.8334 52.2449C49.6875 52.2449 48.75 53.1824 48.75 54.3282C48.75 55.474 49.6875 56.4115 50.8334 56.4115C51.9792 56.4115 52.9167 55.474 52.9167 54.3282Z" fill="white"/>
            </svg>
            <span>
              <b>/install the desktop app</b>
              <p>omni/ runs in the background while you play.</p>
            </span>
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="65" height="65" viewBox="0 0 65 65" fill="none" style="min-width: 60px;">
              <path d="M45.8383 19.3293H19.1677C16.9694 19.329 14.8052 19.8723 12.8677 20.9107C10.9302 21.9491 9.2795 23.4505 8.06259 25.2812C6.84569 27.1119 6.10034 29.2151 5.89288 31.4035C5.68543 33.5919 6.02231 35.7977 6.87354 37.8245C7.72477 39.8512 9.06394 41.636 10.7718 43.02C12.4797 44.404 14.5033 45.3442 16.6624 45.757C18.8216 46.1697 21.0493 46.0422 23.1472 45.3857C25.2451 44.7293 27.1482 43.5642 28.687 41.9944H36.3131C37.8517 43.5641 39.7545 44.729 41.8522 45.3855C43.9498 46.042 46.1773 46.1697 48.3362 45.7572C50.4952 45.3448 52.5187 44.4049 54.2266 43.0214C55.9345 41.6378 57.2738 39.8535 58.1254 37.8271C58.977 35.8008 59.3144 33.5954 59.1075 31.4071C58.9007 29.2189 58.1561 27.1157 56.9399 25.2848C55.7237 23.454 54.0738 21.9522 52.1369 20.9131C50.2 19.8741 48.0363 19.33 45.8383 19.3293ZM26.5005 33.6617C26.5005 33.9269 26.3951 34.1812 26.2076 34.3687C26.0201 34.5562 25.7657 34.6616 25.5005 34.6616H21.1675V38.9946C21.1675 39.2598 21.0622 39.5141 20.8746 39.7017C20.6871 39.8892 20.4328 39.9945 20.1676 39.9945H18.1677C17.9025 39.9945 17.6482 39.8892 17.4607 39.7017C17.2732 39.5141 17.1678 39.2598 17.1678 38.9946V34.6616H12.8348C12.5696 34.6616 12.3152 34.5562 12.1277 34.3687C11.9402 34.1812 11.8349 33.9269 11.8349 33.6617V31.6618C11.8349 31.3966 11.9402 31.1423 12.1277 30.9547C12.3152 30.7672 12.5696 30.6619 12.8348 30.6619H17.1678V26.3288C17.1678 26.0636 17.2732 25.8093 17.4607 25.6218C17.6482 25.4343 17.9025 25.3289 18.1677 25.3289H20.1676C20.4328 25.3289 20.6871 25.4343 20.8746 25.6218C21.0622 25.8093 21.1675 26.0636 21.1675 26.3288V30.6619H25.5005C25.7657 30.6619 26.0201 30.7672 26.2076 30.9547C26.3951 31.1423 26.5005 31.3966 26.5005 31.6618V33.6617ZM44.4992 39.9945C43.84 39.9945 43.1955 39.7991 42.6474 39.4328C42.0993 39.0666 41.6721 38.546 41.4198 37.937C41.1675 37.3279 41.1015 36.6577 41.2301 36.0112C41.3587 35.3646 41.6762 34.7707 42.1423 34.3046C42.6085 33.8384 43.2024 33.521 43.8489 33.3924C44.4955 33.2638 45.1657 33.3298 45.7747 33.5821C46.3837 33.8343 46.9043 34.2615 47.2705 34.8097C47.6368 35.3578 47.8323 36.0022 47.8323 36.6614C47.8323 37.5454 47.4811 38.3932 46.856 39.0183C46.231 39.6434 45.3832 39.9945 44.4992 39.9945ZM49.8321 31.9951C49.1729 31.9951 48.5285 31.7996 47.9804 31.4334C47.4322 31.0671 47.005 30.5466 46.7528 29.9375C46.5005 29.3285 46.4345 28.6583 46.5631 28.0118C46.6917 27.3652 47.0091 26.7713 47.4753 26.3052C47.9414 25.839 48.5353 25.5216 49.1819 25.393C49.8284 25.2644 50.4986 25.3304 51.1077 25.5826C51.7167 25.8349 52.2373 26.2621 52.6035 26.8102C52.9697 27.3584 53.1652 28.0028 53.1652 28.662C53.1652 29.546 52.8141 30.3938 52.189 31.0189C51.5639 31.6439 50.7161 31.9951 49.8321 31.9951Z" fill="white"/>
            </svg>
            <span>
              <b>/play your favorite game(s)</b>
              <p>omni/ captures and uploads your favorite moments.</p>
            </span>
          </li>
          <li>
            <svg xmlns="http://www.w3.org/2000/svg" width="65" height="65" viewBox="0 0 65 65" fill="none">
              <path d="M53.3748 28.3552L16.7096 6.67901C13.7305 4.91866 9.16821 6.62693 9.16821 10.9809V54.3229C9.16821 58.229 13.4076 60.5831 16.7096 58.6248L53.3748 36.959C56.6455 35.032 56.6559 30.2822 53.3748 28.3552Z" fill="white"/>
            </svg>
            <span>
              <b>/share from anywhere</b>
              <p>/share your highlights from our mobile app or website.</p>
            </span>
          </li>
        </ul>
        <footer>
          <button class="primary-btn blue-theme"><Icon name="ri:windows-fill" />&nbsp;&nbsp;Download</button>
          <img src="/omni/rgb-slash.svg" alt="Omnislash RGB Slash" />
        </footer>
      </section>

      <section>
        <label>/connect to your favorite games</label>

        <p></p>
        
        <div id="supported-wrapper">
          <div class="game" v-for="game in games" :key="game.name">
            <img :src="game.src" :alt="game.name" />
            <div class="game-title">
              <b>{{game.name}}</b>
            </div>
          </div>
        </div>

        <p class="small-desc">
          Some gaming accounts may require additional steps to link to your omni/ account. 
          Check out the <a href="https://discord.gg/QZa5xw8" target="_blank" class="reg-link"><b>Discord</b></a> should you need more information or assistance.
        </p>
        
        <footer>
          <button class="primary-btn blue-theme"><Icon name="ri:windows-fill" />&nbsp;&nbsp;Download</button>
          <img src="/omni/rgb-slash.svg" alt="Omnislash RGB Slash" />
        </footer>
      </section>
    </main>
  </div>
</template>


<script setup>
useHead({
  bodyAttrs: {
    style: 'overflow: auto !important; background-color: #1A1D20 !important; color: rgba(255, 255, 255, 0.6) !important;'
  }
})

const games = [
  { name: "League of Legends", src: "/omni/games/lol.png" },
  { name: "Valorant", src: "/omni/games/valorant.png" },
  { name: "Teamfight Tactics", src: "/omni/games/tft.png" },
  { name: "Fortnite", src: "/omni/games/fortnite.png" },
  { name: "Counter-Strike 2", src: "/omni/games/csgo.png" },
  { name: "Hearthstone", src: "/omni/games/hearthstone.png" },
  { name: "Dota 2", src: "/omni/games/dota2.png" },
  { name: "Marvel Snap", src: "/omni/games/marvelsnap.png" },
]
</script>

<style lang="scss" scoped>
@media only screen and (max-width: 590px) {
  main section:first-of-type header {
    justify-content: center;
  }
}

@media only screen and (max-width: 500px) {
  main section:first-of-type #app-desc b {
    margin-top: 8px !important;
    font-size: 20px !important;
  }

  main section:first-of-type #app-desc {
    button span {
      display: none;
    }
  }

  main section#contact {
    button {
      b {
        font-size: 24px !important;
        white-space: normal !important;
      }
      svg {
        width: 32px !important;
      }
      svg.discord-bubble {
        left: 22px !important;
        bottom: 29px !important;
      }
    }
  }

  main section#contact button svg {
    width: 32px;
  }
}

@media only screen and (max-width: 430px) {
  main section ul li {
    flex-direction: column;
    text-align: center;
  }
}

@media only screen and (max-width: 380px) {
  main section footer {
    justify-content: center;
    img {
      display: none;
    }
  }
}

.banner-enter-active,
.banner-leave-active {
  transition: all 4000ms;
}
.banner-enter-from,
.banner-leave-to {
  opacity: 0;
  transform: translateY(80px);
}

.bounce-enter-active,
.bounce-leave-active {
  transition-timing-function: cubic-bezier(.05,1.4,0.8,1.3);
  transition-duration: 5s;
}
.bounce-enter-from,
.bounce-leave-to {
  opacity: 0;
  transform: translate(-30px, 50px);
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.25);
  }
  100% {
    transform: scale(1);
  }
}

main {
  display: flex;
  flex-direction: column;
  align-items: center;
  position: relative;
  z-index: 1;
  margin: 100px 0 120px;
  gap: 32px;
  font-size: 19px;
  font-family: 'Inter', 'Roboto', sans-serif;
  section {
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.1);
    background: rgba(26, 29, 32, 0.85);
    box-shadow: 2px 4px 25.7px 0px #000;
    backdrop-filter: blur(15.5px);
    padding: 24px;
    width: 931px;
    max-width: calc(100vw - 100px);
    position: relative;
    height: fit-content;
    display: unset;
    &:first-of-type {
      background: linear-gradient(180deg, #1A1D20 51.97%, rgba(26, 29, 32, 0.48) 100%);
      #app-desc {
        display: flex;
        flex-direction: column;
        position: relative;
        border-radius: 20px;
        button {
          width: fit-content;
          padding: 0 16px;
          max-width: 100%;
        }
        b {
          color: #ffffff;
          font-size: 32px;
        }
        p {
          margin: 16px 0 24px 0;
          font-size: 20px;
          b {
            color: rgba(255, 255, 255, 0.87);
            svg {
              margin-right: 4px;
            }
          }
        }
        header {
          display: flex;
          align-items: center;
          text-align: center;
          img {
            max-width: 100%;
          }
        }
      }
      #banner {
        display: none;
        width: fit-content;
        background: rgba(0, 163, 255, 0.6);
        position: absolute;
        border: 2px solid #ffffff;
        padding: 16px;
        text-align: center;
        border-radius: 20px;
        box-shadow: 2px 4px 25.7px 0px #000;
        top: -77px;
        right: 10px;
        white-space: nowrap;
        b {
          color: rgba(255, 255, 255, 0.95); 
          font-size: 24px;
        }
        p {
          margin: 0;
          font-size: 16px;
          b {
            font-size: 16px;
          }
        }
      }
    }
    &#contact {
      display: flex;
      flex-direction: column;
      align-items: center;
      background: transparent;
      box-shadow: none;
      border: none;
      backdrop-filter: blur(0.1px);
      padding: 24px 0;
      max-width: calc(100vw - 50px);
      button {
        width: fit-content;
        display: flex;
        align-items: center;
        height: fit-content;
        color: #fff;
        font-weight: normal;
        text-align: left;
        gap: 24px;
        padding: 16px 24px;
        border-radius: 50px;
        box-shadow: 0px 4px 18px 0px rgba(0, 0, 0, 0.75);
        &:hover {
          background: #58648f;
        }
        &:active {
          background: #6a759c;
        }
        svg {
          min-width: 32px;
        }
        b {
          font-size: 32px;
        }
        p {
          color: rgba(255, 255, 255, 0.6);
          margin: 0;
          white-space: normal;
          text-align: left;
        }
        .svg-wrapper {
          position: relative;
          .discord-bubble {
            position: absolute;
            left: 40px;
            bottom: 45px;
          }
        }
      }
      p {
        font-size: 16px;
        margin: 8px 0;
        text-align: center;
        .email-link {
          font-weight: bold;
          color: rgba(255, 255, 255, 0.87);
          white-space: nowrap;
        }
      }
    }
    ul {
      display: flex;
      flex-direction: column;
      list-style: none;
      gap: 24px;
      font-size: 16px;
      padding: 0;
      margin: 0;
      li {
        display: flex;
        align-items: center;
        gap: 16px;
        border-radius: 20px;
        background: rgba(255, 255, 255, 0.05);
        padding: 16px;
        svg {
          min-width: 60px;
        }
        b {
          color: #ffffff;
          font-size: 20px;
          font-family: 'Euclid', 'Roboto', sans-serif;
        }
        p {
          margin: 10px 0 0 0;
        }
      }
    }
    footer {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-top: 24px;
      button {
        height: 35px;
        width: 131px;
      }
    }
    #supported-wrapper {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
    }
    .small-desc {
      margin: 24px 0;
      font-size: 16px;
      padding: 0 16px;
    }
  }
  :deep(#fixed-content) {
    margin-top: -32px;
  }
}

label {
  display: block;
  width: fit-content;
  padding: 6px 24px;
  font-size: 32px;
  font-weight: bold;
  color: #ffffff;
  text-align: center;
}

.primary-btn {
  transition: 200ms ease-out all;
  font-family: "Inter", "Roboto", sans-serif;
  font-weight: bold;
  font-size: 16px;
  mix-blend-mode: screen;
  width: 120px;
  height: 35px;
  border: none;
  outline: none;
  cursor: pointer;
  border-radius: 20px;
  white-space: nowrap;
  color: #000;
  background: #FFFFFF;
  &.discord-theme {
    background: #455383;
  }
}

.game {
  display: flex;
  flex-direction: column;
  padding: 8px;
  border-radius: 20px;
  color: #FFFFFF;
  font-size: 16px;
  cursor: pointer;
  transition: 150ms ease-in all;
  user-select: none;
  text-decoration: none;
  &:hover {
    background: rgba(255, 255, 255, 0.1);
  }
  &:active {
    background: rgba(255, 255, 255, 0.1);
  }
  .game-title {
    display: flex;
    gap: 4px;
    b {
      width: 165px;
    }
    svg {
      max-width: 14px;
    }
  }
  img {
    height: 220px;
    width: 165px;
    border-radius: 20px;
    background: #27282a;
    margin-bottom: 8px;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
  }
  svg {
    margin-bottom: 8px;
  }
}
</style>