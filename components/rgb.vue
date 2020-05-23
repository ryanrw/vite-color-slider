<template>
  <div>
    <div class="color-box" :style="rgbConcatenater"></div>
    <div class="rgb-slider">
      <div class="slider-form">
        <div class="label">Red</div>
        <input :value="red" readonly />
        <input type="range" :min="min" :max="max" v-model="red" />
      </div>
      <div class="slider-form">
        <div class="label">Green</div>
        <input :value="green" readonly />
        <input type="range" :min="min" :max="max" v-model="green" />
      </div>
      <div class="slider-form">
        <div class="label">Blue</div>
        <input :value="blue" readonly />
        <input type="range" :min="min" :max="max" v-model="blue" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.color-box {
  width: 50vw;
  min-width: 300px;
  height: 400px;
  border: 1px solid;
}

.rgb-slider {
  margin-top: 30px;
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}

.rgb-slider .slider-form {
  display: flex;
  align-items: center;
  margin: 5px 0;
}

.rgb-slider input[readonly] {
  width: 30px;
  margin-right: 10px;
}

.label {
  width: 70px;
  display: inline-block;
}
</style>

<script>
export default {
  name: "RGB",
  data() {
    return {
      min: 0,
      max: 255,
      red: 0,
      green: 0,
      blue: 0,
    };
  },
  computed: {
    rgbConcatenater: function () {
      return `background: rgb(${this.red}, ${this.green}, ${this.blue})`;
    },
  },
};
</script>
