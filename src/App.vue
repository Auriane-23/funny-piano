<template>
  <div id="app" class="text-center m-auto pt-10 w-full h-full">
    <v-text></v-text>
    <v-piano></v-piano>
  </div>
</template>

<script>
import VText from '@/components/VText'
import VPiano from '@/components/VPiano'

export default {
  name: 'App',
  components: {
    VPiano,
    VText,
  }
}
</script>

<style lang="postcss" scoped>
#app {
  font-family: 'PT Mono', monospace ;
  background: linear-gradient(135deg, #FF9D6C 0%, #BB4E75 100%) ;
}
</style>