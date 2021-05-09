<template>
  <div class="portfolioMain">
    <h1>つくったもの</h1>
    <div class='portfolioArea'>
      <PortfolioBlock v-for='(p,i) of portfolio' :key='i'
      :title='p.title' :img='p.img' :video='p.video' :text='p.text' :index='i' />
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
        その小路綾の発言を形態素解析し、マルコフ連鎖により小路綾らしい発言を生成するプログラムです。
        twitterでは、10分に一度ランダムに生成したテキストを投稿する機能、リプライを受け取りそのテキストを形態素解析し、
        動詞等を抜き取りその単語から開始される文章を生成し擬似的に会話をすることができる機能が搭載されています。
        精度に関してはいいとは言えないかもしれませんが意図は読み取れる程度の文章は生成できています。
        アカウントが凍結されてしまい現存はしません`
        },
        {
          title:'IoTハウス横浜',
          
          video:require('../assets/yokohama.mp4'),
          text:`自宅の廊下の天井にテープLEDを引き、それをraspberrypiのGPIOからトランジスタを介して操作しています。
          壁のスイッチにサーボモータを設置し、部屋備え付けの電灯も制御下に置いています。
          また玄関に磁石スイッチを設置し、ドアの開閉を検知しそれをトリガーに電気がつくようになっています。
          またraspberrypiにはhttpリクエストから操作できるようなプログラムが入っており、wifiネットワーク下であればブラウザから電灯が操作できます。
          またraspberrypiに併設したslackbotにメッセージが来るとそこからhttpリクエストを送られ、これにより外部からでも操作ができます。
          そのslackbotをiftttによりgoogleHomeから、つまり声で操作することもできます。
          横浜からは引越したため現存しませんが今の家もIoT化しようと画策している最中です。`,
        },
        {
          title:'このページ',
          img: require('../assets/logo.png'),
          text:`vueをおすすめされ、チュートリアル一周後練習がてら作ってみました。
          そんなに複雑なことはしていませんが2年前に作ったポートフォリオサイトよりかなり簡素に凝ったものが作れて驚いています。
          フロントはまだまだ全然出来ませんがこれを機に知識を深めていけたら良いなと思っています。`,
        },
        {
          title:'非接触給電',
          video: require('../assets/inductive.mp4'),
          text:`誘導電流を使用し、回路的に接続されていないLEDを点灯させる回路です。
          ネットで興味を惹かれた回路を組んでみることがありますが動作原理など考えてみると非常に興味深いです。`,
        },
        {
          title: 'モールス電灯',
          video: require('../assets/morse.mp4'),
          text: `部屋の照明にセパラボディとソリッドステートリレーを噛ませて操作できるようにしました。
          2つの照明を一つのスイッチから操作したかったため単純なオンオフではなくモールス信号に着想を得た操作法をします。
          '-'で全点灯、'･'で消灯、'--･'/'-･-'で片方が点灯します。
          これを作ったときはインターネット環境がテザリングのみで不安定だったのでarduinoで完結するように組みました。
          仕組みを知らない友人を部屋に入れてarduinoごと落とされてもデフォルトを通電にしているので問題なく可動することが可能です`
        }
      ]
    }
  }
}
</script>

<style scoped>
.portfolioMain{
  text-align: center;
  display: inline-block;
}
.portfolioArea{
  margin:0px;

  text-align: center;
  display: inline-block;
}

/*
@media screen and (min-width: 800px) {
  .portfolioArea {
      margin:0px;
      width: 700px;
      }
}
*/


</style>
