<template>
  <div class="mainWrapper">
    <img src="@/assets/frame.png" class="frameImg" draggable="false" @mousedown="startUnlock" @mouseup="stopUnlock" @mouseleave="stopUnlock" />
    <div class="minigameWrapper">
      <div class="minigameContainer">
        <div class="lockMod" :style="`transform: rotate(${rotation}deg);`">
          <img src="@/assets/lock.png" class="lockImg" />
          <img src="@/assets/tension.png" class="tensionImg" :style="`transform: rotateZ(${(rotation/5)}deg) rotateX(${rotation/4}deg) rotateY(${rotation/4}deg);`" />
          <img src="@/assets/pick.png" class="pickImg" :style="`transform: rotateZ(${pickRotation-(rotation/2)}deg);`" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LockpickMiniGame',
  props: {
    rotation: {
      default: 0
    },
    pickRotation: {
      default: 0
    }
  },
  methods: {
    startUnlock: function(){
      console.log("starting to unlock")
    },
    stopUnlock: function(){
      console.log("stopping unlock")
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.mainWrapper{
  position: relative;
  .frameImg{
    max-width: 50vw;
    max-height: 45vh;
  }
  .frameImg:hover{
    cursor: pointer;
  }
}
.minigameWrapper{
  display: flex;
  align-items: center;
  justify-content: center;
  pointer-events: none;
  position: absolute;
  width: 100%;
  height: 100%;
  top:0;
  left:0;

  .minigameContainer{
    //background-color: #47474d;
    //border: 2px solid rgba(0,0,0,0.2);
    //border: 1px solid yellow;
    border-radius: 2%;
    width: 55.4%;
    height: 65%;
    position: absolute;
    left: 31.7%;
    top: 15.7%;
    //display: none;

    .lockMod{
      width: 100%;
      height: 100%;
      position: absolute;
      display: flex;
      align-items: center;
      justify-content: center;
      .lockImg{
        max-width: 100%;
        max-height: 100%;
        position: absolute;
      }
      .tensionImg{
        max-width: 100%;
        max-height: 100%;
        position: absolute;
        left: 49%;
        top: 54%;
        transform-origin: 0% 0%;
      }
      .pickImg{
        max-width: 110%;
        max-height: 110%;
        position: absolute;
        right: auto;
        left: auto;
        bottom: 54%;
        transform-origin: 50% 100%;
      }
    }
  }
}


</style>
