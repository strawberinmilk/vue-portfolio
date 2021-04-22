<template>
  <div class="portfolioMain">
    <h1>つくったもの</h1>
    <div class='portfolioArea'>
      <PortfolioBlock v-for='(p,i) of portfolio' :key='i'
      :title='p.title' :img='p.img' :text='p.text' :index='i' />
    </div>
    <img alt="Vue logo" src="../assets/logo.png">
  </div>
</template>

<script>
import PortfolioBlock from './PortfolioBlock.vue'
export default {
  name: 'Portfolio',
  components: {
    PortfolioBlock,
  },
  data() {
    return{
      portfolio:[
        {
          title:'小路綾bot',
          img: require('../assets/komichiayabot.png'),
          text:`小路綾とは、"きんいろモザイク"という漫画、アニメの登場人物です。
        その小路綾の発言を形態素解析し、マルコフ連鎖により小路綾らしい発言を生成するプログラムです。<br />
        現在はtwitterに投稿するコードのみ動かしていますが、slackへ投稿するプログラムもgithubに上がっています。<br />
        twitterでは、10分に一度ランダムに生成したテキストを投稿する機能、リプライを受け取りそのテキストを形態素解析し、
        動詞等を抜き取りその単語から開始される文章を生成し擬似的に会話をすることができる機能が搭載されています。<br />
        精度に関してはいいとは言えないかもしれませんが意図は読み取れる程度の文章は生成できています。`
        },
        {
          title:'IoTハウスat横浜',
          img: require('../assets/logo.png'),
          text:`自宅の廊下の天井にテープLEDを引き、それをraspberrypiのGPIOからトランジスタを介して操作しています。<br>
    また玄関に磁石スイッチを設置し、ドアの開閉を検知しそれをトリガーに電気がつくようになっています。<br>
    またraspberrypiにはhttpリクエストから操作できるようなプログラムが入っており、wifiネットワーク下であればブラウザから電灯が操作できます。<br>
    また下記のslackbotからhttpリクエストを送ることにより外部からでも操作ができます。<br>
    そのslackbotをiftttによりgoogleHomeから、つまり声で操作することもできます。<br>`,
        },
        {
          title:'title2',
          img: require('../assets/logo.png'),
          text:'',
        },
        {
          title:'title3',
          img: require('../assets/logo.png'),
          text:'',
        },
        {
          title:'title4',
          img: require('../assets/logo.png'),
          text:'',
        },
        {
          title:'title5',
          img: require('../assets/logo.png'),
          text:'',
        },
      ]
    }
  }
}
</script>

<style scoped>
.portfolioMain{
  text-align: center;
}
.portfolioArea{
  background-color: magenta;

}
</style>
