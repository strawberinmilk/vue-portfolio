<template>

  <transition name="slide-up" v-for='i of 3' :key=i>
  <div class='back' v-if='i+0<count&&count<title.length' v-bind:style='{backgroundColor: `${color[i/*Math.floor(Math.random()*color.length+1)*/]}`,}'/>
  </transition>
  
  <transition name="slide-down" v-for='i of 3' :key=i>
  <div class='back' v-if='i+5<count&&count<title.length' v-bind:style='{backgroundColor: `${color[i+3/*Math.floor(Math.random()*color.length+1)*/]}`,}'/>
  </transition>

  <transition name="slide-up" v-for='i of 3' :key=i>
  <div class='back' v-if='i+10<count&&count<title.length' v-bind:style='{backgroundColor: `${color[i+6/*Math.floor(Math.random()*color.length+1)*/]}`,}'/>
  </transition>

  <div class="topMain">
    <h1>
      <span v-for='(char, index) in title' :key=index v-show='index<count'>{{char}}</span>
    </h1> 
  
  <transition name="slide-up">
  <div class='linkArea' v-if='title.length<count' v-bind:style='{backgroundColor: `${color[i+6/*Math.floor(Math.random()*color.length+1)*/]}`,}'>
    <h3>
      <transition name="slide-up" v-for='i of message.length+1' :key=i>
        <span v-if='i+title.length<count'>{{message[i-1]}}</span>
      </transition>
    </h3>
    
  </div>
  </transition>
  </div>
  

</template>

<script>

export default {
  name: 'Top',
  components: {
  },
  data(){
    return{
      count:0,
      title:'                    rin.     の   portfolio '.split(''),
      message:'右のメニューをホバーしお進みください→'.split(''),
      color:[
        'cyan',
        'yellowgreen',
        'yellow',
        'darkblue',
        'red',
        'green',
        'gray',
        'salmon',
        'hotpink',
        'pink',
        'gold',
      ],
      pageList:{
        //top:{name:'top', path:'Top', display: 'top',show:true},
        portfolio:{name:'portfolio', path:'Portfolio', display: 'portfolio',show:false},
        about:{name: 'about', path:'About', display:'about', show:false},
      }

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
.back{
  background-color: magenta;
  position: absolute;
  top:0px;
  left:0px;
  height:100%;
  width:100%;
  margin:0px;
}
.topMain{
  position: relative;
  text-align: center;
}

.linkArea{
  width:80%;
  height:200px;
  margin-left:10%;
  margin-right:10%;
  margin-top:30%;
}
.slide-up-enter-active,
.slide-down-enter-active {
  transition: all 0.5s ease-in;
}

.slide-up-leave-active,
.slide-down-leave-active {
  transition: all 0.5s ease-out;
}

.slide-up-enter-from{
  transform: translate(0%,100%);
  opacity: 0;
}
.slide-up-leave-to{
  transform: translate(0%,100%);
  opacity: 0;
}

.slide-down-enter-from{
  transform: translate(0%,-100%);
  opacity: 0;
}
.slide-down-leave-to{
  transform: translate(0%,100%);
  opacity: 0;
}

</style>
