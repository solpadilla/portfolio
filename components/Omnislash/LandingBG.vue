<template>
  <div id="bg-wrapper" :style="{top: top ? top + 'px' : ''}">
    <div id="left">
      <img src="/omni/bg/1.png" alt="Super Animal Royale" />
      <img src="/omni/bg/3.png" alt="Street Fighter 6" />
      <img src="/omni/bg/5.png" alt="MultiVersus" />
      <img src="/omni/bg/7.png" alt="Elden Ring" />
      <img src="/omni/bg/9.png" alt="Diablo 4" />
      <img src="/omni/bg/11.png" alt="Baldur's Gate 3" />
      <img src="/omni/bg/13.png" alt="Crusader Kings 3" />
    </div>
    <div id="right">
      <img src="/omni/bg/2.png" alt="Warframe" />
      <img src="/omni/bg/4.png" alt="Path of Exile" />
      <img src="/omni/bg/6.png" alt="Killing Floor 2" />
      <img src="/omni/bg/8.png" alt="Human: Fall Flat" />
      <img src="/omni/bg/10.png" alt="DREDGE" />
      <img src="/omni/bg/12.png" alt="Cult of the Lamb" />
      <img src="/omni/bg/14.png" alt="Paladins" />
    </div>
  </div>
</template>

<script setup>
const props = defineProps({ 
  top: { 
    default: '0' 
  } 
});
</script>

<style scoped lang="scss">
#bg-wrapper {
  display: flex;
  justify-content: center;
  width: 100vw;
  gap: 16px;
  position: fixed;
  top: 100px;
  div {
    width: min-content;
  }
  img {
    min-width: 752px;
    height: 225px;
    filter: blur(27px);
    transition: 300ms ease-out all;
    &:hover {
      filter: blur(6px);
    }
  }
}
</style>