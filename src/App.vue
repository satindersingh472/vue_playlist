<template>
  <div id="app">
    <!-- using a song display component -->
  <song-display></song-display>
  </div>
</template>

<script>
// importing a songdisplay component
import SongDisplay from '@/components/songDisplay.vue'


export default {
  name: 'App',
  components: {
    SongDisplay

  }
}
</script>

<style>
#app{
  background-color: bisque;
}
</style>
