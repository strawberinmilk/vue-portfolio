<template>
  <div class='starMain'>
    <transition name="star">
      <div class='star' v-bind:style='{ top: `${Math.floor(Math.random()*100)}%`, color: `${color[Math.floor(Math.random()*color.length+1)]}` }'>
        <h1 class='starSpan'>★</h1>
      </div>
    </transition>
  </div>
</template>

<script>

export default {
  name: 'Star',
  data(){
    return{
      star:true,
      color:[
        'magenta',
        'cyan',
        'yellowgreen',
        'yellow',
        'darkblue',
        'red',
        'green',
      ]
    }
  },
  mounted(){
    //setInterval(()=>{
      //this.star = !this.star
    //},2000)
  }
}
</script>

<style scoped>
.starMain{
  position: fixed;
  top:0px;
  left:-20px;
  height: 100%;
  width:100%;
  pointer-events: none;

}

@keyframes rotate {
  0% {
    transform:rotate(0deg);
  }
  100% {
    transform:rotate(360deg);
  }
}

@keyframes move {
  0% {
    transform:translateX(-20%);
  }
  50% {
    transform:translateX(120%);

  }
  100% {
    transform:translateX(-20%);
  }
}
.star{
  position: absolute;
  width:100%;
  left:0%;
  animation: move 10s infinite linear;

}
.starSpan{
  animation: rotate 5s infinite linear;
  position:relative;
  height:100px;
  width:100px;
  size:100px;
  opacity : 0.5;
}
.star-enter-active {
  transition: all 0s ;
}

.star-leave-active {
  transition: all 20s ;
}

.star-enter-from,
.star-leave-to {
  transform: translateX(150%);
}
</style>
