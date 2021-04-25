<template>
  <div class="selectArea" v-on:mouseover="selectMouseOver()" v-on:mouseleave="selectMouseLeave()">
    <div class='inline triangle'>◀</div>

    <div class='inline selectBoxArea'>
      <div>
      <Select v-for="page of pageList" v-bind:key="page.name" v-bind:name='page.name' v-bind:path='page.path' v-bind:display='page.display' v-on:changePage="changePage($event)"/>
      </div>
    </div>
  </div>
</template>

<script>
import Select from './Select.vue'

export default {
  name: 'SelectArea',
  components: {
    Select
  },
  data(){
    return{
        pageList:{
        top:{name:'top', path:'Top', display: 'top',show:true},
        portfolio:{name:'portfolio', path:'Portfolio', display: 'portfolio',show:false},
        about:{name: 'about', path:'About', display:'about', show:false},
      }
    }
  },
  methods:{
    changePage(val){
      this.$emit('changePage', val);
    }
  },
}
</script>

<style scoped>  
.selectArea{
  background-color:#E0FFFF;
  position: fixed;
  top:50%;
  left:calc(100% - 80px);
  width:300px;
  transition: left 0.5s;

  border-radius:30px;
}
.selectArea:hover{
  left:calc(100% - 300px);
}
.triangle{
  margin:10px;
  height:60px;
  width: 60px;
  font-size:60px;
}
.inline{
  text-align: center;
  display: inline-block;
}
.selectBoxArea{
  width:160px;
}
</style>
