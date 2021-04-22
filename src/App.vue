<template>
  <Background />

  <transition name="slide-fade">
  <Top v-show='nowContent==="top"' />
  </transition>
  <transition name="slide-fade">
  <Portfolio v-show='nowContent==="portfolio"' />
  </transition>
  <transition name="slide-fade">
  <About v-show='nowContent==="about"' />
  </transition>
  

  <SelectArea v-on:changePage="changePage($event)"/>

</template>

<script>
import Top from './components/Top.vue'
import Portfolio from './components/Portfolio.vue'
import About from './components/About.vue'

import SelectArea from './components/SelectArea.vue'
import Background from './components/Background.vue'

export default {
  name: 'App',
  components: {
    Top,
    Portfolio,
    About,
    SelectArea,
    Background,
  },
  data(){
    return {
      nowContent: 'top',
    }
  },
  methods: {
    changePage(val) {
      if(this.nowContent === val) return;
      this.nowContent = val
    },
  },

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
  transition: all 0s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(100px);
  opacity: 0;
}

</style>
