<template>
<div class="profile">
  <v-app-bar
    fixed
    app
    dark
    color="black"
    elevation="0"
  >
    <v-app-bar-title v-text="title"/>
    <v-spacer/>
    <v-btn
      v-for="link in links"
      :key="link.name"
      plain
      color="white"
      :to=link.to
    >
      {{link.name}}
    </v-btn>
  </v-app-bar>
  <v-main>
    <v-row>
      <v-col cols="3">
        <v-row >
          <v-avatar size="300" style="margin: 0 auto;"><img src="../static/pheasant.jpg"></v-avatar>
          <v-card elevation="0">
            <v-card-title >Profile</v-card-title>
            <v-card-text>
              <div v-for="item in about" :key="item.head">
                <v-row>
                  <v-col cols="3">
                    {{item.head}}
                  </v-col>
                  <v-col cols="9">
                    {{item.main}}
                  </v-col>
                </v-row>
              </div>
            </v-card-text>
          </v-card>
        </v-row>
      </v-col>
      <v-col cols="9">
        <v-row justify="start">
        <v-timeline>
          <v-timeline-item
            v-for="(hist, i) in histories"
            :key="i"
            :color="hist.color"
            right
            small
          >
            <template v-slot:opposite>
              <span
                :class="`headline font-weight-bold ${hist.color}--text`"
                v-text="hist.year"
              ></span>
            </template>
            <div class="py-4">
              <h2 :class="`headline font-weight-light mb-4 ${hist.color}--text`">
                {{hist.head}}
              </h2>
              {{hist.main}}
            </div>
          </v-timeline-item>
        </v-timeline>
        </v-row>
      </v-col>
    </v-row>
  </v-main>
</div>
</template>

<script>
export default {
  layout: 'top',
  data(){
    return{
      title: 'woodnext',
      about:[
        {head: "WHAT?", main: "ゲームやWebシステムなどいろいろ作る人 エンジニアの卵（?）"},
        {head: "HOW?", main: "C/C++, Unity(C#), Vue.js(JavaScript), Ruby...などなど 並びは好きな順番"},
        {head: "WHERE?", main: "鳥取県出身 現在は高専生 情報工学を専攻しています"},
        {head: "WHEN?", main: "2020年ごろからプログラミングを本格的に始めました"},
        {head: "WHY?", main: "こんなものがあったら面白いな，便利だなと思いながら作っています"},
      ],
      histories: [
        {color: 'green', year: '2002', head: 'BIRTH', main: '鳥取県に生まれる'},
        {color: 'red', year: '2009~', head: 'ORIGIN', main: '折り紙やペーパークラフトを作り始める 自分のモノづくりの原点'},
        {color: 'blue', year: '2018', head: 'KOSEN', main: '松江高専 情報工学科入学'},
        {color: 'orange', year: '2021', head: 'PROGRAMMING-CONTEST', main: '高専プロコンにサブメンバーとして参加，特別賞（全国3位相当）を受賞'},
        {color: 'blue', year: '2023', head: 'UNIVERCITY', main: '高専卒業，○○大学に入学（予定）'},
      ],
      links: [
        {name: 'Top', disabled: false, to: '/'}, 
        {name: 'About me', disabled: false, to: '/profile'}, 
        {name: 'Works', disabled: true, to: '/works'}, 
        {name: 'Hobbies', disabled: true, to: 'hobbies'},
      ],
    }
  }
}
</script>

<style scoped>
.profile{
  padding: 3%;
}
</style>
