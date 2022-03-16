<template>
    <div class="paciens">
        <div class="container">
            <h2 class="paciens_title title">Выберите количество пациентов на прием</h2>
            <div class="paciens__inner flex-column frame-wrapper">
                <input class="slider" type="range" min="300" max="1900" v-model="this.value">
                <div class="numbers"></div>
            </div>
            <div class="input-wrapper flex">
                <p>Приемы: </p>
                <input class="input-test" type="number" v-model="this.value">
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: "Frame-third",
  data() {
    return {
      value: 300
    }
  },
  methods: {
  }
}
</script>

<style scoped>
.numbers {
    background-image: url(../assets/img/numbers.svg);
    background-size: contain;
    background-repeat: no-repeat;
    width: 100%;
    height: 70px;
    margin-top: 10px;
}
.slider {
    margin-top: 30px;
}
.input-test {
  font-size: 30px;
  width: 100px;
}
.input-wrapper {
  justify-content: space-between;
  margin-top: 30px;
  font-size: 30px;
}
input[type=range].slider {
  width: 100%;
  margin: 17.5px 0;
  background-color: transparent;
  -webkit-appearance: none;
}
input[type=range].slider:focus {
  outline: none;
}
input[type=range].slider::-webkit-slider-runnable-track {
  background: #26a69a;
  border: 0;
  width: 100%;
  height: 8px;
  cursor: pointer;
}
input[type=range].slider::-webkit-slider-thumb {
  margin-top: -17.5px;
  width: 43px;
  height: 43px;
  background: #26a69a;
  border: 0px solid rgba(0, 30, 0, 0);
  border: 0;
  border-radius: 25px;
  cursor: pointer;
  -webkit-appearance: none;
}
input[type=range].slider:focus::-webkit-slider-runnable-track {
  background: #28aea2;
}
input[type=range].slider::-moz-range-track {
  background: #26a69a;
  border: 0;
  width: 100%;
  height: 8px;
  cursor: pointer;
}
input[type=range].slider::-moz-range-thumb {
  width: 43px;
  height: 43px;
  background: #26a69a;
  border: 0px solid rgba(0, 30, 0, 0);
  border: 0;
  border-radius: 25px;
  cursor: pointer;
}
input[type=range].slider::-ms-track {
  background: transparent;
  border-color: transparent;
  border-width: 18.3px 0;
  color: transparent;
  width: 100%;
  height: 8px;
  cursor: pointer;
}
input[type=range].slider::-ms-fill-lower {
  background: #249e92;
  border: 0;
}
input[type=range].slider::-ms-fill-upper {
  background: #26a69a;
  border: 0;
}
input[type=range].slider::-ms-thumb {
  width: 43px;
  height: 43px;
  background: #26a69a;
  border: 0px solid rgba(0, 30, 0, 0);
  border: 0;
  border-radius: 25px;
  cursor: pointer;
  margin-top: 0px;
  /*Needed to keep the Edge thumb centred*/
}
input[type=range].slider:focus::-ms-fill-lower {
  background: #26a69a;
}
input[type=range].slider:focus::-ms-fill-upper {
  background: #28aea2;
}
/*TODO: Use one of the selectors from https://stackoverflow.com/a/20541859/7077589 and figure out
how to remove the virtical space around the range input in IE*/
@supports (-ms-ime-align:auto) {
  /* Pre-Chromium Edge only styles, selector taken from hhttps://stackoverflow.com/a/32202953/7077589 */
  input[type=range].slider {
    margin: 0;
    /*Edge starts the margin from the thumb, not the track as other browsers do*/
  }
}

</style>