<template>
  <div class="container">
    <div class="card">
      <div class="upper-card">
        <span class="block uppercase views">
          {{ rangeNumber }} Pageviews
        </span>
        <div class="slider">
          <input id="input" type="range" min="0" value="2" max="4" step="1" @change="setStep()">
          <div id="output" hidden>
          </div>
        </div>
        <div class="price-content flex items-center">
          <span class="bolder price">
            $16.00
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
      rangeNumber: 100000
    }
  },
  methods: {
    setStep(){
      let values = [10000,50000,100000,500000,1000000];    //values to step to

      const input = document.getElementById('input');
      let output = document.getElementById('output');

      input.oninput = function(){
          output.innerHTML = values[this.value];
      };
      input.oninput(); //set default value

      this.rangeNumber = output.innerHTML;
    },
  },

};
</script>

<style lang="scss">
@import '/src/assets/sass/_app';

  .card-content {
  position: relative;
  z-index: 10;
  margin: 0 auto;

  h1 {
    font-weight: $font-lg;
    font-size: rem(26px);
    color: $dark-saturated-blue;
    padding-top: rem(95px);
    padding-bottom: rem(16px);
  }

  .heading-2 {
    h2 {
      color: $grayish-blue;
      font-weight: $font-md;
      font-size: rem(16px);

      &:not(:last-of-type) {
        margin-bottom: rem(6px);
      }
    }
  }

  .price-content {
    margin-bottom: rem(44px);
  }

  .price {
    margin-right: rem(10px);
    font-size: rem(45px);
    color: $dark-saturated-blue;
    letter-spacing: rem(- 1.5px);
  }

  .check {
    margin-bottom: 14px;
  }

  .check-icon {
    margin-right: rem(20px);

    img {
      width: 10px;
      height: 10px;
    }
  }
}

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
</style>
