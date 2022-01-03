<template>
  <div class="app">
    <Countdown />
  </div>
</template>

<script>
import Countdown from './components/Countown.vue'

export default {
  name: 'App',
  components: {
    Countdown
  }
}
</script>

<style>

    :root{
  --clr-bg1:#252525FF;
  --clr-bg2:#3B3B3BFF; 
  --clr-main:#0fff;
  --clr-main2:#00C4F0FF;
  --clr-text:#E4E4E4FF;
}

.app{
  padding-top: 150px !important;
  background: var(--clr-bg1);
  color: var(--clr-text);
  height: 100vh;
  width: 100%;
  overflow: hidden;
  
}


</style>