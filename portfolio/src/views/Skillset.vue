<template>
  <div class="skillset">
    <v-container fluid style="overflow: auto; position: fixed; box-sizing: border-box; left: 0px; top: 40px; right: 0px; bottom: 0px; width: 100vw; height: 100vh; background-color: rgba(0, 0, 0, 0.75); color: rgb(232, 232, 232);">
      <h1 style="margin: 10px;">my skillset</h1>




      <h3 class="sub">language</h3>
      <v-row class="row">
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/python.png"></v-img>
            <v-card-title>python -main-</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>機械学習システムとの連携等</div>
              <div>flaskを用いたAPI実装、機械学習のデータ整形、画像認識モデルの作成</div>
            </v-card-text>
        </v-card>
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/java.png"></v-img>
            <v-card-title>java</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>簡易的な掲示板作成、書籍管理システムの作成</div>
              <div></div>
            </v-card-text>
        </v-card>
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/kotlin.png"></v-img>
            <v-card-title>kotlin</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>パズルアプリ作成で勉強（android）</div>
              <div></div>
            </v-card-text>
        </v-card>
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/js.png"></v-img>
            <v-card-title>javascript</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>管理サイト画面等</div>
              <div>Ajax通信を主に勉強</div>
            </v-card-text>
        </v-card>
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/html_css.png"></v-img>
            <v-card-title>html, css</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>社内サイト系の簡素なデザイン作成経験のみ</div>
              <div>最近UI, UXに興味を持ち、jsと共に勉強中</div>
            </v-card-text>
        </v-card>
      </v-row>






      <h3 class="sub">framework</h3>
      <v-row class="row">
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/flask.png"></v-img>
            <v-img contain class="subimg" src="@/static/python.png"></v-img>
            <v-card-title>flask</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>ユーザーがaws serviceを利用する窓口として、flask apiを作成</div>
              <div></div>
            </v-card-text>
        </v-card>
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/vue.jpg"></v-img>
            <v-img contain class="subimg" src="@/static/js.png"></v-img>
            <v-card-title>vue.js</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>このサイトを作成するのに使用</div>
              <div>vue.jsの勉強を通して、他のjsフレームワークへ理解を広げたい今日この頃</div>
            </v-card-text>
        </v-card>
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/react.png"></v-img>
            <v-img contain class="subimg" src="@/static/js.png"></v-img>
            <v-card-title>react native</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>一瞬触った程度</div>
              <div>スマホのパズルアプリ作成（クロスプラットフォーム）</div>
            </v-card-text>
        </v-card>
      </v-row>



      <h3 class="sub">service</h3>
      <v-row class="row">
        <v-card class="mx-left card" max-width="160">
            <v-img contain class="img" src="@/static/aws.png"></v-img>
            <v-card-title>AWS -main-</v-card-title>
            <v-card-subtitle>経験年数：1年未満</v-card-subtitle>
            <v-card-text>
              <div>アーキテクチャの提案から開発までを経験中</div>
              <div>コストを意識したバッチ処理や、疎結合で変更に強いアーキテクチャを意識した導入を心がけている</div>
            </v-card-text>
        </v-card>
      </v-row>


    </v-container>
  </div>
</template>

<style scoped>
  .row {
    margin-top: 10px;
    margin-bottom: 50px;
    margin-left: 0px;
    margin-right: 0px;
  }
  .card {
    margin: 10px 10px;
    float: left;
  }
  .sub {
    margin: 10px;
    text-decoration: underline;
  }
  .img {
    margin: 0 auto;
    height: 100px;
    width: 150px
  }
  .subimg {
    height: 30px;
    width: 30px
  }
</style>
