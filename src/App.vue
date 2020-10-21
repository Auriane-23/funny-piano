<template>
  <div id="app" class="w-screen h-screen bg-gradient-to-r from-orange to-rose">
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
    VText
  }
}
</script>

<style lang="postcss" scoped>

</style>