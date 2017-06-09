<template>
  <div id="app">
    <h1>TROYES.JS</h1>
    <h1>Progressive Web App</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod<br>
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,<br>
      quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo<br>
      consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse<br>
      cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non<br>
      proident, sunt in culpa qui officia deserunt mollit anim id est laborum.<br>
    </p>
    <h1>Web font loading</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod<br>
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,<br>
      quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo<br>
      consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse<br>
      cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non<br>
      proident, sunt in culpa qui officia deserunt mollit anim id est laborum.<br>
    </p>
    <h1>Image loading</h1>
    <div class="troyes-imgs">
      <troyes-image
        dominantColor="#c69d63"
        width="840"
        height="525"
        low="http://i.imgur.com/mjpQ0YY.jpg"
        src="http://i.imgur.com/tEvhHuS.jpg"></troyes-image>
      <troyes-image
        dominantColor="#b29b86"
        width="840"
        height="525"
        low="http://i.imgur.com/VqAsg3J.jpg"
        src="http://i.imgur.com/I31jOZx.jpg"></troyes-image>
    </div>
    <h1>Ghost content</h1>
    <div class="troyes-tags">
      <troyes-card-placeholder bin="https://api.myjson.com/bins/l935x"></troyes-card-placeholder>
      <troyes-card-placeholder bin="https://api.myjson.com/bins/xr6v9"></troyes-card-placeholder>
      <troyes-card-placeholder bin="https://api.myjson.com/bins/yy22t"></troyes-card-placeholder>
    </div>
    <h1>Critical content</h1>
    <div class="troyes-rects">
      <div class="line" v-for="(_, u) in [0, 0, 0, 0, 0, 0, 0, 0]">
        <div class="rect" :id="id(u, i)" v-for="(_, i) in [0, 0, 0, 0, 0]"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Image from './Image.vue'
import CardPlaceholder from './CardPlaceholder.vue'

const arr = (function* () {
  return yield* [...Array(40).keys()]
}())

export default {
  name: 'app',

  components: {
    'troyes-image': Image,
    'troyes-card-placeholder': CardPlaceholder
  },

  methods: {
    id(u, i) {
      return `rect${arr.next().value + 1}`;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  font-size: 16px;
  font-size-adjust: .5;
  font-family: sans-serif;
  margin: 0;
  line-height: 1.21;
}

h1 {
  font-family: cursive;
  font-size: 40px;
  line-height: 40px;
  font-size-adjust: unset;
}

#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.troyes-imgs {
  display: flex;
}

.troyes-tags {
  background: #fff;
  display: flex;
  padding: 40px 10px;
}

.troyes-tags > .troyes-card-placeholder-wrapper {
  flex: 1;
  margin: 0 10px;
}

.troyes-rects {
  display: flex;
  flex-direction: column;
}

.troyes-rects > .line {
  display: flex;
  flex-direction: row;
  margin: 10px 0;
  padding: 0 10px;
}

.troyes-rects > .line > .rect {
  background-color: #39c;
  margin: 0 10px;
  height: 100px;
  flex: 1;
}

.troyes-rects > .line > #rect1 {
  background-color: #a93027;
}

.troyes-rects > .line > #rect2 {
  background-color: #57ce35;
}

.troyes-rects > .line > #rect3 {
  background-color: #29dd79;
}

.troyes-rects > .line > #rect4 {
  background-color: #ce3d26;
}

.troyes-rects > .line > #rect5 {
  background-color: #fd10e0;
}

.troyes-rects > .line > #rect6 {
  background-color: #a3c591;
}

.troyes-rects > .line > #rect7 {
  background-color: #6a15c2;
}

.troyes-rects > .line > #rect8 {
  background-color: #49dc3f;
}

.troyes-rects > .line > #rect9 {
  background-color: #88f946;
}

.troyes-rects > .line > #rect10 {
  background-color: #574fa4;
}

.troyes-rects > .line > #rect11 {
  background-color: #5de67b;
}

.troyes-rects > .line > #rect12 {
  background-color: #db5b2f;
}

.troyes-rects > .line > #rect13 {
  background-color: #2e75af;
}

.troyes-rects > .line > #rect14 {
  background-color: #b81239;
}

.troyes-rects > .line > #rect15 {
  background-color: #440190;
}

.troyes-rects > .line > #rect16 {
  background-color: #8bb2cc;
}

.troyes-rects > .line > #rect17 {
  background-color: #668984;
}

.troyes-rects > .line > #rect18 {
  background-color: #35243f;
}

.troyes-rects > .line > #rect19 {
  background-color: #260032;
}

.troyes-rects > .line > #rect20 {
  background-color: #951fd9;
}

.troyes-rects > .line > #rect21 {
  background-color: #fd8871;
}

.troyes-rects > .line > #rect22 {
  background-color: #61311a;
}

.troyes-rects > .line > #rect23 {
  background-color: #3dde11;
}

.troyes-rects > .line > #rect24 {
  background-color: #0890ff;
}

.troyes-rects > .line > #rect25 {
  background-color: #7e5b16;
}

.troyes-rects > .line > #rect26 {
  background-color: #e8fae1;
}

.troyes-rects > .line > #rect27 {
  background-color: #3aeee8;
}

.troyes-rects > .line > #rect28 {
  background-color: #553f23;
}

.troyes-rects > .line > #rect29 {
  background-color: #b153f1;
}

.troyes-rects > .line > #rect30 {
  background-color: #b3b941;
}

.troyes-rects > .line > #rect31 {
  background-color: #0d4ad3;
}

.troyes-rects > .line > #rect32 {
  background-color: #7653c1;
}

.troyes-rects > .line > #rect33 {
  background-color: #be9fd2;
}

.troyes-rects > .line > #rect34 {
  background-color: #dde8ca;
}

.troyes-rects > .line > #rect35 {
  background-color: #f24527;
}

.troyes-rects > .line > #rect36 {
  background-color: #9e9429;
}

.troyes-rects > .line > #rect37 {
  background-color: #2f8d42;
}

.troyes-rects > .line > #rect38 {
  background-color: #d1d8cb;
}

.troyes-rects > .line > #rect39 {
  background-color: #ee10b9;
}

.troyes-rects > .line > #rect40 {
  background-color: #682566;
}

.wf-active body {
  font-family: 'Catamaran', sans-serif;
  line-height: 1.3;
  font-size: 16px;
  font-size-adjust: .5;
}

.wf-active h1 {
  font-family: 'Pacifico', cursive;
  font-size: 36px;
}
</style>
