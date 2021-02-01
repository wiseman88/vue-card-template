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

      <card-component></card-component>
    </div>
    <footer-component></footer-component>
    </div>
  </div>
</template>

<script>
import FooterComponent from './components/FooterComponent'
import CardComponent from './components/CardComponent'

export default {
  name: 'App',
  components: {
    FooterComponent,
    CardComponent
  }
}
</script>

<style lang="scss">
@import '/src/assets/sass/_app';

.wrapper {
  background-color: $very-pale-blue;
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

.slider {
  padding-top: rem(45px);
}

.views {
  letter-spacing: rem(1px);
  font-weight: $font-lg;
}

</style>
