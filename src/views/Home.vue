<template>
  <div class="home">
    <input type="range" max="90" min="0" v-model="rotation"/>
    <LockpickMiniGame :rotation="rotation" :pickRotation="pickRotation" />
    <input type="range" max="80" min="-80" v-model="pickRotation"/>
  </div>
</template>

<script>
// @ is an alias to /src
import LockpickMiniGame from '@/components/lockpickMiniGame.vue'

export default {
  name: 'home',
  components: {
    LockpickMiniGame
  },
  data(){
    return {
      rotation: 0,
      pickRotation: 0
    }
  }
}
</script>

<style scoped lang="scss">
.home{
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  background-color: #666;
}
</style>
