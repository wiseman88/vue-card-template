<template>
  <div class="wrapper">
    <div class="bg">

    </div>
    <div>
      <div class="card-content">
      <h1>
      Simple, traffic-based pricing
      </h1>
      <div class="heading-2">
        <h2>
          Sign-up for our 30-day trial.
        </h2>
        <h2>
          No credit card required. 
        </h2>
      </div>

      <div class="container">
        <div class="card">
          <span class="block uppercase views">
            100K Pageviews
          </span>
          <div class="slider">

          </div>
          <div class="price-content flex items-center">
            <span class="bolder price">
              $16
            </span>
            <span>/month</span>
          </div>

          <switch-component></switch-component>

          Unlimited websites
          100% data ownership
          Email reports

          Start my trial
        </div>
      </div>
    </div>
    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
      Coded by <a href="#">Your Name Here</a>.
    </div>
    </div>
  </div>
</template>

<script>
import SwitchComponent from './components/SwitchComponent'

export default {
  name: 'App',
  components: {
    SwitchComponent
  }
}
</script>

<style lang="scss">
@import '/src/assets/sass/_app';

.wrapper {
  background-color: $white;
  position: relative;
  text-align: center;
  z-index: 1;
  height: 100vh;
}

.bg {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 0;
  min-height: 55vh;
  width: 100%;
  background-image: url('./assets/img/bg-pattern.svg');
  background-size: cover;
  background-position: 0 -85px;
  background-repeat: no-repeat;
}

.card-content {
  position: relative;
  z-index: 10;
  margin: 0 auto;

  h1 {
    font-weight: $font-lg;
    font-size: rem(26px);
    color: $dark-saturated-blue;
    padding-top: rem(95px);
    padding-bottom: rem(25px);
  }

  .heading-2 {
    h2 {
      color: $grayish-blue;
      font-weight: $font-md;
      font-size: rem(16px);

      &:not(:last-of-type) {
        margin-bottom: rem(14px);
      }
    }
  }

  .price-content {
    margin-bottom: rem(44px);
  }

  .price {
    margin-right: rem(10px);
    font-size: rem(30px);
    color: $dark-saturated-blue;
  }
}

.card {
  display: inline-block;
  border-radius: 20px;
  margin-top: rem(70px);
  padding-top: rem(39px);
  padding-left: rem(24px);
  padding-right: rem(24px);
  padding-bottom: rem(33px);
  background-color: $white;
  color: $grayish-blue;
  box-shadow: 0 0 10px 0 rgba(0,0,0, .05);
}

.slider {
  padding-top: rem(45px);
}

.views {
  letter-spacing: rem(1px);
  font-weight: $font-lg;
}

</style>
