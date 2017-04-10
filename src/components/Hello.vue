<template>
  <div class="hello">
    <div class="head">
      <img src="../assets/img/mingyi.png" />
    </div>

    <div class="h-title">
      <h2>搜狗AI口腔实验室</h2>
      <h1>诊断证明</h1>
    </div>

    <div class="split"></div>

    <div class="p-data">
      <div class="p-data-left">
        <div>
          <!-- <div class="p-data-c">
            <p>姓名：</p>
            <p class="p-data-c-data">{{name}}</p>
          </div> -->
          <div class="p-data-c">
            <p>性别：</p>
            <p class="p-data-c-data">{{gender}}</p>
          </div>
          <div class="p-data-c">
            <p>年龄：</p>
            <p class="p-data-c-data">{{age}}</p>
          </div>
        </div>
        <p class="p-data-cong">祝贺您成为搜狗AI口腔实验室的第  {{player}}  位体检员</p>
      </div>
      <div class="p-data-right">
        <img v-bind:src="imageData" />
      </div>
    </div>

    <div class="split"></div>

    <div class="content">
      <p class="title">检测报告如下：</p>
      <ul class="c-detail">
        <li>
          <p>1. 基本资料</p>
          <div class="c-detail-data">
            <p>口腔魅力值<span class="c-detail-c-data">{{mouthScore}}</span>，</p>
            <p>颜值分数<span class="c-detail-c-data">{{faceScore}}</span>。</p>
            <p class="c-desc">{{mouthDesc}}</p>
          </div>
        </li>

        <li>
          <p>2. 常规检测</p>
          <div class="c-detail-data">
            <p>魔音魅力值<span class="c-detail-c-data">{{sound}}</span>。</p>
            <p class="c-desc">{{soundDesc}}</p>
          </div>
        </li>

        <li>
          <p>3. 深度检测</p>
          <div class="c-detail-data">
            <p>口齿准确度<span class="c-detail-c-data">{{fluency}}</span>。</p>
            <p class="c-desc">{{twisterDesc}}</p>
          </div>
        </li>
      </ul>

      <p class="c-detail-bottom">感谢您见证搜狗AI技术取得的巨大成就。</p>

      <img class="stamp" src="../assets/img/stamp.png" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',

  created() {
    let id = this.$route.query.id
    this.$http.get('http://share.robot.sogou.com/load?id=' + id).then(response => {
      this.name = response.body.name
      this.gender = response.body.gender
      this.age = response.body.age
      this.player = response.body.player
      this.imageData = 'data:image/png;base64,' + response.body.image_data
      this.mouthScore = response.body.mouth_score
      this.faceScore = response.body.face_score
      this.sound = response.body.db
      this.fluency = response.body.twister_score + '%'
      this.mouthDesc = response.body.mouth_desc
      this.soundDesc = response.body.sound_desc
      this.twisterDesc = response.body.twister_desc
    })
  },

  data () {
    return {
      name: '',
      gender: '',
      age: '',
      player: '',
      mouthScore: '',
      faceScore: '',
      sound: '',
      fluency: '',
      imageData: '',
      mouthDesc: '',
      soundDesc: '',
      twisterDesc: '',
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

.head img {
  height: 1em;
}

.h-title {
  text-align: center;
}

h1 {
  font-size: 2em;
  letter-spacing: 0.3em;
  margin-bottom: 0.3em;
}

h2 {
  font-size: 1.5em;
  margin-top: 0.5em;
}

.split {
  width: 100%;
  height: 2px;
  background: #f33344
}

.p-data {
  text-align: left;
  margin: 1em 0 2em 0;
  position: relative;
}

.p-data-left, .p-data-right {
  display: inline-block;
  vertical-align: middle;
}

.p-data-left {
  width: 75%;
  position: relative;
  left: 0.3em;
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

.p-data-right {
  position: absolute;
  right: 0.3em;
}

.p-data-right img {
  background: #dcdcdc;
  height: 6.4rem;
  width: 4.8rem;
}

.p-data-cong {
  color: #f33344;
  font-size: 0.7em;
  position: relative;
  max-width: 90%;
  bottom: -2em;
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
  margin-bottom: 1.5em;
}

.c-detail-data p {
  display: inline-block;
}

.c-detail-bottom {
  font-size: 0.6em;
  opacity: 0.7;
  margin: 0 3%;
  padding-left: 1.5em;
  max-width: 58%;
}

.c-detail-c-data {
  display: inline-block;
  min-width: 3em;
  text-align: center;
  border-bottom: 1px dashed black;
}

.stamp {
  width: 8em;
  float: right;
  position: relative;
  top: -5em;
  right: -1em;
}

.c-desc {
  opacity: 0.7;
  font-size: 0.6em;
  max-width: 78%;
}
</style>
