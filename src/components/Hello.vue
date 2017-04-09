<template>
  <div class="hello">
    <div class="head">
      <img src="" />
      <p>搜狗明医</p>
    </div>

    <div class="h-title">
      <h2>搜狗AI口腔实验室</h2>
      <h1>诊断证明</h1>
    </div>

    <div class="split"></div>

    <div class="p-data">
      <div class="p-data-left">
        <div>
          <div class="p-data-c">
            <p>性别：</p>
            <p class="p-data-c-data">{{gender}}</p>
          </div>
          <div class="p-data-c">
            <p>年龄：</p>
            <p class="p-data-c-data">{{age}}</p>
          </div>
        </div>
        <p class="p-data-cong">祝贺您成为搜狗AI口腔实验室的第  {{count}}  位体检员</p>
      </div>
      <div class="p-data-right">
        <img src="" />
      </div>
    </div>

    <div class="split"></div>

    <div class="content">
      <p class="title">检测报告如下：</p>
      <ul class="c-detail">
        <li>
          <p>1. 基本资料</p>
          <div class="c-detail-data">
            <p>口腔魅力值<span class="c-detail-c-data">{{mouth}}</span>，</p>
            <p>颜值分数<span class="c-detail-c-data">{{face}}</span>。</p>
          </div>
        </li>

        <li>
          <p>2. 常规检测</p>
          <div class="c-detail-data">
            <p>魔音魅力值<span class="c-detail-c-data">{{sound}}</span>。</p>
          </div>
        </li>

        <li>
          <p>3. 深度检测</p>
          <div class="c-detail-data">
            <p>口齿准确度<span class="c-detail-c-data">{{fluency}}</span>。</p>
          </div>
        </li>
      </ul>

      <p class="c-detail-bottom">感谢您见证搜狗AI技术取得的巨大成就。</p>

      <img class="stamp" src="" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      gender: '男',
      age: 18,
      count: 88,
      mouth: 100,
      face: 100,
      sound: 100,
      fluency: 100,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
  color: #f33344;
}

.head {
  text-align: left;
}

.head * {
  display: inline-block;
}

.h-title {
  text-align: center;
}

h1 {
  font-size: 2em;
  letter-spacing: 0.3em;
}

h2 {
  font-size: 1.5em;
  margin-top: 1em;
}

.split {
  width: 100%;
  height: 2px;
  background: #f33344
}

.p-data {
  text-align: left;
  margin: 2em 0;
}

.p-data-left, .p-data-right {
  display: inline-block;
  vertical-align: middle;
}

.p-data-left {
  width: 70%;
  position: relative;
  left: 1em;
}

.p-data-left p {
  margin-top: 0.4em;
}

.p-data-c p {
  display: inline-block;
}

.p-data-c-data {
  min-width: 5em;
  text-align: center;
  border-bottom: 1px dashed black;
}

/*.p-data-c-data::after {
  content: '- - - - - - -';
  position: relative;
  left: -1em;
  top: 1em;
}*/

.p-data-right {
  width: 20%;
}

.p-data-right img {
  background: #dcdcdc;
  min-height: 8em;
}

.p-data-right img {
  width: 100%;
}

.p-data-cong {
  color: #f33344;
  font-size: 0.7em;
  position: relative;
  bottom: -4em;
}

.content {
  margin-top: 1em;
  text-align: left;
}

.c-detail {
  list-style: none;
  margin: 0.3em 3%;
}

.c-detail-data {
  margin-left: 1em;
  margin-bottom: 3em;
}

.c-detail-data p {
  display: inline-block;
}

.c-detail-bottom {
  font-size: 0.6em;
  opacity: 0.7;
  margin: 0 3%;
  padding-left: 1.5em;
}

.c-detail-c-data {
  display: inline-block;
  min-width: 3em;
  text-align: center;
  border-bottom: 1px dashed black;
}
</style>
