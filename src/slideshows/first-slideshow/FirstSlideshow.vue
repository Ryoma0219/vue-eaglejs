<template lang='pug'>
#MyFirstSlideshow.eg-theme-gourmet
  .eg-slideshow
    slide(enter='fadeIn')
      br
      h1 I'm Ryoma !
      br
      eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
        h4 This is my first slideshow !
      br
      eg-transition(enter='bounceInLeft' leave='bounceOutLeft')
        h4 iPhoneXS 買ったあああああ !

    slide(enter='bounceInRight' leave='fadeOut')
      h3 Second slideshow
      <br>
      p.
        今日食べた麻婆豆腐めちゃ美味しかったわ<br>
        It was delicious that I ate today's lunch !
      div.button-area
        b-button(@click="showAlert()") Push Me !
      b-alert(v-if="alertShown" show variant="info") bootstrap もいれてみた

    slide.local-eg-theme-ryoma-hoshino(enter='fadeIn' leave='fadeOut')
      eg-transition(enter='fadeInLeft' leave='fadeIn')
        div
          h3 Softly<br> as in a morning sunrise

    slide.local-eg-theme-ryoma-hoshino2(:steps=6, enter='bounceInDown')
      h3 Should learn to accomplish
      br

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if='step >=2')
          img(src='https://upload.wikimedia.org/wikipedia/commons/f/f1/Vue.png'
              :style="{height: '5em'}")
          h4 Vue.js
          p Develop Front End App

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if='step >=3')
          img(src='https://about.gitlab.com/images/press/logo/logo.png'
              :style="{height: '5em'}")
          h4 Gitlab
          p Version Control, CI

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if="step >= 4")
         img(src='https://sdtimes.com/wp-content/uploads/2018/02/golang.sh_-490x490.png'
            :style="{height: '5em'}")
         h4 Go lang
         p Develop Back End App

      eg-transition(enter='fadeIn' leave='fadeOut')
        .quarter(v-if="step >= 5")
          img(src='https://nodejs.org/static/images/logos/nodejs-new-pantone-black.png'
              :style="{height: '5em'}")
          h4 Node.js
          p Anywhere

      eg-transition(enter='fadeIn' leave='fadeOut')
        eg-modal(v-if='step >= 6')
          .center
            div こんなかんじです。本当になんでもできる！
            div そのほかはデモをご覧ください！

</template>

<script>
import eagle from 'eagle.js'
export default {
  mixins: [ eagle.slideshow ],
  infos: {
    // These infos appear on the home page, below the slideshow's thumbnail
    title: 'はじめてのEagleスライド',
    description: 'Vue * Eagle.jsでSPAスライド',
    path: 'your-first-slideshow'
  },
  data () {
    return {
      alertShown: false,
      preloadedImages: {
        computerKid: 'https://i.imgur.com/AAlntwU.gif',
        youRightNow: 'https://i.imgur.com/3gnrERb.mp4',
        bretagne: 'https://i.imgur.com/rYkJ6I8.jpg',
        forrestRoad: 'https://i.imgur.com/hxTMFZW.jpg',
        starrySky: 'https://i.imgur.com/yO2ivoD.jpg',
        cityBokeh: 'https://i.imgur.com/kmmHith.jpg',
        darkWoods: 'https://i.imgur.com/FL9mwpd.jpg',
        pushButton: 'https://i.imgur.com/KaAyvZ5.gif'
      }
    }
  },
  methods: {
    showAlert () {
      this.alertShown = !this.alertShown
    }
  }
}
</script>

<style lang='scss'>
@import url(https://fonts.googleapis.com/css?family=Raleway|Roboto+Mono);
#MyFirstSlideshow{
  .eg-slideshow{
    font-family: 'Roboto Mono'!important;
    background-color: #eef;
    .eg-slide{
      .eg-slide-content{
        width: 25em;
        max-width: 80%;
      }
    }
  }
  .eg-slide-content{
    width: 25em;
    max-width: 80%;
    margin: 0 auto;
  }
  .button-area{
    text-align: center;
  }

  .local-eg-theme-ryoma-hoshino {
    @import url(https://fonts.googleapis.com/css?family=Pacifico);
    h3 {
      font-family: 'Pacifico';
      margin-top: 50%;
      text-align: left;
      color: rgba(255, 255, 255, .9);
    }
    div {
      margin: 0 10%;
    }
    background-image: url('./assets/mountaion.jpg');
    background-position: center;
    background-size: cover;
  }
  .local-eg-theme-ryoma-hoshino2 {
    @import url(https://fonts.googleapis.com/css?family=Vidaloka|Roboto+Mono);
    h3 {
      font-family: 'Vidaloka';
      color: rgba(0, 0, 0, 0.9);
    }
    .quarter {
      text-align: center;
      p {
        margin-top: 0;
        text-align: center;
      }
      h4 {
        margin-top: 0;
        margin-bottom: 0
      }
    }
    .boredYet {
      p {
        margin-bottom: 0.3em;
        margin-top: 1.3em;
      }
      .button {
        border: none;
      }
      .button.prev {
        float: left;
      }
      .button.next {
        float: right;
      }
    }
    .center {
      margin-top: 10%;
    }
    img.computerkid {
      height: 6.5em;
    }
    h4, p {
      font-family: 'Roboto Mono';
      color: rgb(0, 0, 0)
    }
    background-image: url('./assets/boke.jpg');
    background-position: center;
    background-size: cover;
    font-family: 'Josefin Slab';
    color: rgb(254, 255, 184)
  }
}
</style>
