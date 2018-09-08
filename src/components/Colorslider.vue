<template>
  <div>
    <header class="WholeBody">
        <h1> VUE STYLE </h1>
      <header  :style="titleStyle">Your Color Value Is : HSL({{this.hue}}, {{this.saturation}}, {{this.lightness}})</header>
    </header>
    <section>
      <section class="Main-Picker">
        <div class="TheActualBox" :style="boxStyle" >  
        </div>
          <section>
            <div class="ValueBox">Hue:</div>
            <input 
              type="range" 
              min="0" 
              max="360"
              v-on:input="this.HueValue"
              :value="this.hue" />
            <div class="ValueBox">Saturation:</div>
            <input 
              type="range"
              min="0" 
              max="100"
              v-on:input="SaturationValue"
              :value="this.saturation" />
            <div class="ValueBox">Lightness:</div>
            <input 
              type="range" 
              min="0" 
              max="100"
              v-on:input="LightnessValue"
              :value="this.lightness" />
          </section>
      </section> 
    </section>
  </div>
</template>

<script>
export default {
  name: "ColorPicker",
  data: function() {
    return {
      hue: 180,
      saturation: 50,
      lightness: 50,
    }
  },
  methods: {
    HueValue: function (event){
      return this.hue = event.target.value
    },
    SaturationValue: function (event){
      return this.saturation = event.target.value
    },
    LightnessValue: function (event){
      return this.lightness = event.target.value
    },
  },
  computed: {
    boxStyle: function() {
      return {
        "background-color": "HSL(" + this.hue + ", " + this.saturation + "%, " + this.lightness + "%)",
      };},
    titleStyle: function() {
      return {
        "color": "HSL(" + this.hue + ", " + this.saturation + "%, " + this.lightness + "%,)",
      };}
  },
};
</script>

<style scoped>
.WholeBody {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  color: rgb(30, 30, 83);
  margin-bottom: 1em;
  padding: 1em;
  font-size: 28px;
}

.TheActualBox {
  background-color: black;
  height: 35em;
  width: 20em;
  border: .2em solid black;
}
.ValueBox {
  font-size: 18px;
  color: rgb(30, 30, 83);
}
.Main-Picker {
  display: flex;
  justify-content: center;
}

input {
  display: flex;
  text-align: center;
  margin-bottom: 2em;
  width: 25em;
  padding: 2em;
}
.ColorInputs {
  margin-top: 0.8em;
  margin-left: auto;
  margin-right: auto;
  width: 12em;
  font-size: .8em;
  border: 1px solid #222;
  border-radius: 4px;
}
</style>
