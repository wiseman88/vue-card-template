<template>
  <div class="container">
    <div class="card">
      <div class="upper-card">
        <span class="block uppercase views">
          {{ rangeNumber.views }} Pageviews
        </span>
        <div class="slider">
          <input id="input" type="range" min="0" value="2" max="4" step="1" @change="setStep()">
          <div id="output" hidden>
          </div>
        </div>
        <div class="price-content flex items-center">
          <span class="bolder price">
            ${{rangeNumber.price}}.00
          </span>
          <span>/ month</span>
        </div>

        <switch-component></switch-component>
      </div>

      <div class="bottom-card">
        <div class="flex items-center check">
          <span class="check-icon flex items-center">
            <img src="../assets/img/icon-check.svg" alt="">
          </span>
          <span>Unlimited websites</span>
        </div>
        <div class="flex items-center check">
          <span class="check-icon flex items-center">
            <img src="../assets/img/icon-check.svg" alt="">
          </span>
          <span>100% data ownership</span>
        </div>
        <div class="flex items-center check">
          <span class="check-icon flex items-center">
            <img src="../assets/img/icon-check.svg" alt="">
          </span>
          <span>Email reports</span>
        </div>
        <button class="btn">
          Start my trial
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import SwitchComponent from './SwitchComponent'
export default {
  name: 'CardComponent',
  components: {
    SwitchComponent
  },
  data(){
    return {
      rangeNumber: {
        views: '100K',
        price: '16',
      },
      rangeSliderData: [
        {
          views: '10K',
          price: '8'
        },
        {
          views: '50K',
          price: '12'
        },
        {
          views: '100K',
          price: '16'
        },
        {
          views: '500K',
          price: '20'
        },
        {
          views: '1M',
          price: '24'
        },
      ]
    }
  },
  methods: {
    setStep(){
      let values = ['10K','50K','100K','500K','1M'];    //values to step to

      const input = document.getElementById('input');
      let output = document.getElementById('output');

      input.oninput = function(){
          output.innerHTML = values[this.value];
      };
      input.oninput(); //set default value

      this.rangeNumber.views = output.innerHTML;

      this.rangeSliderData.forEach(data => {
        switch (this.rangeNumber.views) {
          case data.views:
            this.rangeNumber.price = data.price 
            break;
        }
      });
    },
  },

};
</script>

<style lang="scss">
@import '/src/assets/sass/_app';

.card {
  display: inline-block;
  border-radius: 20px;
  margin-top: rem(70px);
  background-color: $white;
  color: $grayish-blue;
  box-shadow: 0 0 10px 0 rgba(0,0,0, .05);
}

.upper-card {
  padding-top: rem(39px);
  padding-left: rem(20px);
  padding-right: rem(20px);
  padding-bottom: rem(39px);
  border-bottom: 1px solid $light-grayish-blue;
}

.bottom-card {
  padding-top: rem(39px);
  padding-left: rem(20px);
  padding-right: rem(20px);
  padding-bottom: rem(39px);
}

.slider {
  position: relative;
  margin-bottom: rem(30px);
}

input[type='range'] {
  -webkit-appearance: none; 
  width: 100%;
  background-color: $soft-cyan;
  outline: none;
  height: rem(8px);
  border-radius: rem(20px);

  &::-webkit-slider-thumb {
    position: relative;
    -webkit-appearance: none;
    height: rem(40px);
    width: rem(40px);
    border-radius: 50%;
    background: $strong-cyan;
    background-image: url('../assets/img/icon-slider.svg');
    background-repeat: no-repeat;
    background-position: center center;
    cursor: pointer;
    margin-top: -2px;
    -webkit-box-shadow: 1px 14px 23px 5px rgba(16,213,194,0.34); 
box-shadow: 1px 14px 23px 5px rgba(16,213,194,0.34);
  }
}
</style>
