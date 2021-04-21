<template>
  <div class='backgroundMain'>
    <Star v-for='i of 100' v-bind:key='i' v-show='i<count'/>

  </div>
</template>

<script>

import Star from './Star.vue'

export default {
  name: 'Background',
  components: {
    Star
  },
  data(){
    return{
      count: 0,
    }
  },
  mounted(){
    setInterval(()=>{
      this.count++
    },100)
  }
}
</script>

<style scoped>
.backgroundMain{
  position: fixed;
  top:0px;
  left:0px;
  height: 100%;
  width:100%;
  pointer-events: none;
}
</style>
