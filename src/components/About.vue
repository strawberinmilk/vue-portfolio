<template>
  <div class="aboutMain">

    <div class='iconArea'>
      <img class='icon' alt="my icon" src="../assets/icon.png">
      <h1 class='iconName'>rin.</h1>
      <br>
      Illust by <a href='https://twitter.com/masutate_nix'>@Masutate_Nix</a>
    </div>
    
    <h3>わたしについて</h3>
    <p>
    所謂ITエンジニアです
    </p><p>
    各種自動化やIoTに関心が強く、部屋は引っ越すたびにIoT化しています
    </p><p>
    電子工作の中でPICマイコンに触れたことからITの世界に入りました
    </p><p>    
    その後フロントを少しやったところでNode.jsにハマり今に至ります
    </p><p>    
    以前の仕事ではTypeScriptのツール制作から電子工作まで幅広く扱わせていただきました
    </p>
    
    <div class='infoParent' v-for='(info, infoIndex) of information' :key="info">
      <h3>{{infoIndex}}</h3>
      <div class='inline' v-for='(tec, index) of info' :key='index'>
        <h5>{{index}}</h5>
        <ul>
        <li class='card' v-for='t of tec' :key='t'>{{t}}</li>
        </ul>
      </div>
    </div>

    <div class='infoParent'>
      <h3>Link</h3>
      <div class='inline' v-for='(href, index) of link' :key='index'>
        <a class='card' v-bind:href=href>{{index}}</a>
      </div>
      
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'About',
  data(){
    return {
      information:{
        technology:{
          仕事でさわった: [
            'Node.js',
            'TypeScript',
            'arduino言語',
            '電子工作',
          ],
          ちょっとできる: [
            'HTML',
            'css',
            'jquery',
            'vue',
          ],
          はーどうぇあ: [
            'ThinkPad',
            '英語配列KB',
            'raspberryPi',
            'ESP32',
          ],
          しかく: [
            'now studing...'
          ]
        },
        自己紹介:{
          でーた: [
            '誕生日:1999/05/28',
            '持病:統失/心臓疾患',
            'シャンプー:PANTENE',
            '出身:千葉県北西部',
            '在住:東京都23区内',
            'にゃーん'
          ],
          すき:[
            'ubuntu(開発環境)',
            'windows(GUI)',
            'Visual Studio Code',
            'チーズケーキ',
            '可愛いお洋服',
            'きんいろモザイク'
          ],
          きらい: [
            'ubuntu(GUI)',
            'powerShell',
            'mac',
            '変な電圧のACアダプタ',
            'コンパイル',
            'ネジの多いノートPC'
          ],
        }
      },
      link:{
        twitter: ['https://twitter.com/strawbeRinMilk'],
        github: ['https://github.com/6terabyte'],
        amazon: ['https://www.amazon.co.jp/hz/wishlist/ls/9A75OFYW2EJI?ref_=wl_share'],
      }
    }
  }
}
</script>

<style>
.aboutMain{
  text-align: center;
}

.iconArea{
  text-align: center;
  position: relative;
  left: calc(50% - 200px);
  height:330px;
  width:400px;
}
.icon{
  height:300px;
  width:300px;
}
.iconName{
  float:right;
  position:relative;
  top:100px;
}

.infoParent{
  position:relative;
  width:60%;
  left:20%;
  margin: 20px;
  background: rgb(206, 255, 128, 0.5);
  box-shadow: 0px 0px 0px 5px #d6ebff;
  border: dashed 2px white;
}
.inline{
  display: inline-block;
  vertical-align: top;
  margin-left:30px;
  margin-right: 30px;
}
.card{
  color: #404040;
  border-left: solid 5px rgb(140, 127, 255);
  border-bottom: solid 2px #999999;
  background: whitesmoke;
  margin-bottom: 5px;
  line-height: 2;
  padding: 0.5em;
  list-style-type: none;
}
</style>
