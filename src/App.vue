<template>
  <div class="wrapper">
    <div class="bg">

    </div>
    <div>
      <div class="card-wrapper">
      <div>
        <div class="circles"></div>
        <h1 class="heading-1">
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
  min-height: 100vh;
}

.bg {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 0;
  min-height: 55%;
  width: 100%;
  background-image: url('./assets/img/bg-pattern.svg');
  background-size: cover;
  background-position: 0 -85px;
  background-repeat: no-repeat;
}


.card-wrapper {
  position: relative;
  z-index: 10;
  margin: 0 auto;

  h1 {
    font-weight: $font-lg;
    font-size: rem(20px);
    color: $dark-saturated-blue;
    padding-top: rem(95px);
    padding-bottom: rem(16px);
  }

  .heading-2 {
    h2 {
      color: $grayish-blue;
      font-weight: $font-md;
      font-size: rem(14px);

      &:not(:last-of-type) {
        margin-bottom: rem(6px);
      }
    }
  }

  .check {
    margin: rem(12px) 0;
  }

  .check-icon {
    margin-right: rem(20px);

    img {
      width: 10px;
      height: 10px;
    }
  }
}

.circles {
  position: absolute;
  z-index: -1;
  width: 145px;
  height: 145px;
  left: 0; 
  right: 0;
  top: rem(60px); 
  margin-left: auto; 
  margin-right: auto; 
  background-image: url('./assets/img/pattern-circles.svg');
  background-size: contain;
  background-repeat: no-repeat;
}

</style>
