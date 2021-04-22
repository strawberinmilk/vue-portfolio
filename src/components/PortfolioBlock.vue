<template>
  <div class="portfolioMain">
    <div class="portfolioBlock">
      <div class="portfolioSquare" :style='{order:`${index%2?1:2}`}'>
        <img v-bind:src=img />
      </div>
      <div class="portfolioSquare" :style='{order:`${!(index%2)?1:2}`}'>
        <h3> {{title}} </h3>
        {{text}}
        {{img}}
        {{index}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Portfolio",
    props: {
    title: String,
    img: String,
    text: String,
    index: Number,
  },
};
</script>

<style scoped>
.portfolioMain{
  margin:0px;
  max-width:1200px;
}
.portfolioBlock {
  background-color: yellow;
  vertical-align: top;
  margin:0px;
  display: flex;
  flex-wrap:wrap-reverse;
}
.portfolioSquare {
  height: 600px;
  width: 600px;
  background-color: cyan;
  margin: 0px;
  display: inline-block;
  vertical-align: top;
  flex-shrink: 0;
  overflow-wrap: break-word;
}
.portfolioSquare img {
  height: 600px;
  width: auto;
  max-width: 100%;
  max-height: 100%;
  vertical-align: top;
}
</style>
