<template>
  <div id="app">
    <div id="controller">
      <div class="box">
        <p>Box1</p>
        <p>
          <span>大きさ：</span>
          <input v-model="box1.range" type="range" max="500" min="10" />
          <span>{{ box1.range }}</span>
        </p>
        <p>
          <span>赤：</span>
          <input v-model="box1.red" type="range" max="255" min="10" />
          <span>{{ box1.red }}</span>
        </p>
        <p>
          <span>緑：</span>
          <input v-model="box1.green" type="range" max="255" min="10" />
          <span>{{ box1.green }}</span>
        </p>
        <p>
          <span>青：</span>
          <input v-model="box1.blue" type="range" max="255" min="10" />
          <span>{{ box1.blue }}</span>
        </p>
        <p>
          <span>不透明度：</span>
          <input v-model="box1.alpha" type="range" max="100" min="10" />
          <span>{{ box1.alpha }}</span>
        </p>
      </div>

      <div class="box">
        <p>Box2</p>
        <p>
          <span>大きさ：</span>
          <input v-model="box2.range" type="range" max="500" min="10" />
          <span>{{ box2.range }}</span>
        </p>
        <p>
          <span>色相：</span>
          <input v-model="box2.hue" type="range" max="360" min="0" />
          <span>{{ box2.hue }}</span>
        </p>
        <p>
          <span>彩度：</span>
          <input v-model="box2.satulation" type="range" max="100" min="0" />
          <span>{{ box2.satulation }}</span>
        </p>
        <p>
          <span>明度：</span>
          <input v-model="box2.lightness" type="range" max="100" min="0" />
          <span>{{ box2.lightness }}</span>
        </p>
        <p>
          <span>不透明度：</span>
          <input v-model="box2.alpha" type="range" max="100" min="10" />
          <span>{{ box2.alpha }}</span>
        </p>
      </div>
    </div>

    <div :style="bindStyle">
      <div :style="bindStyle2"></div>
    </div>
  </div>
</template>

<script>
export default {
  el: "#app",
  data() {
    return {
      box1: {
        range: 10,
        red: 0,
        blue: 0,
        green: 0,
        alpha: 50,
      },
      box2: {
        range: 10,
        hue: 0,
        satulation: 50,
        lightness: 50,
        alpha: 50,
      },
    };
  },
  methods: {},
  computed: {
    bindStyle() {
      const box = this.box1;
      return `width:${box.range}px; height: ${
        box.range
      }px; background-color: rgba(${box.red}, ${box.green}, ${box.blue}, ${
        box.alpha / 100
      });`;
    },
    bindStyle2() {
      const box = this.box2;
      return `width:${box.range}px; height: ${
        box.range
      }px; background-color: hsla(${box.hue}, ${box.satulation}%, ${
        box.lightness
      }%, ${box.alpha / 100});`;
    },
  },
};
</script>

<style>
.box {
  display: table-cell;
  vertical-align: middle;
  padding: 10px;
}

.controller {
  width: 100%;
  display: table;
  table-layout: fixed;
}
</style>
