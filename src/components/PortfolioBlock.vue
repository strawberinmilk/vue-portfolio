<template>
  <div class="portfolioMain">
    <div class="portfolioBlock">
      <div class="portfolioSquare" :style='{order:`${index%2?1:2}`}'>
        <img class='squareMedia' i-if=img v-bind:src=img />
        <video class='squareMedia' i-if=vide v-bind:src=video loop autoplay muted/>
      </div>
      <div class="portfolioSquare" :style='{order:`${!(index%2)?1:2}`}'>
        <h3> {{title}} </h3>
        <p v-for='line in text.split("\n")' v-bind:key='line' >{{line}}</p>
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
    video: String,
    text: String,
    index: Number,
  },
};
</script>

<style scoped>
.portfolioMain{
  margin:0px;
  width:auto;
  max-width:1300px;
}

@media (max-width: 1300px) {
  .portfolioBlock {
    width:615px;
  }
}
.portfolioBlock {
  vertical-align: top;
  margin:0px;
  display: flex;
  flex-wrap:wrap;
  background-color:rgb(158, 0, 132, 0.3);
}
.portfolioSquare {
  height: 600px;
  width: 600px;
  background-color: rgba(255, 147, 214, 0.3);
  margin: 0px;
  display: inline-block;
  vertical-align: top;
  flex-shrink: 0;
  overflow-wrap: break-word;
  border: dashed 2px white;
  margin: 5px;
}
.squareMedia {
  height: 600px;
  width: auto;
  max-width: 100%;
  max-height: 100%;
  vertical-align: top;
}

</style>
