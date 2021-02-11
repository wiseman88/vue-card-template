<template>
  <div id="switch-content" class="flex items-center">
    <span>Monthly Billing</span>
    <div class="block">
      <label class="switch">
        <input type="checkbox">
        <span class="switch-slider round"></span>
      </label>
    </div>
    <div>
      Yearly Billing <div class="discount">-25% <span>discount</span></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'SwitchComponent',
};
</script>

<style lang="scss">
@import '/src/assets/sass/_app';

  #switch-content {
    
    margin-left: rem(100px);

    @media(max-width: 1439px){
      margin-left: rem(21px);
    }

    * {
      font-size: rem(14px);
    }
  }

  .switch {
  position: relative;
  display: inline-block;
  width: 54px;
  height: 28px;
  margin: 0 20px;

    .switch input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  /* The slider */
  .switch-slider {
    position: absolute;
    cursor: pointer;
    top: rem(2px);
    left: 0;
    right: 0;
    bottom: 0;
    height: rem(26px);
    background-color: $pale-blue;
    -webkit-transition: .4s;
    transition: .4s;
  }

  .switch-slider:before {
    position: absolute;
    content: "";
    height: rem(18px);
    width: rem(18px);
    left: 5px;
    bottom: 4px;
    background-color: white;
    -webkit-transition: .4s;
    transition: .4s;
  }

  input[type=checkbox] {
    margin-top: 5px;
    
  }

  input:hover + .switch-slider {
    background-color: $strong-cyan;
  }

  input:focus + .switch-slider {
    box-shadow: 0 0 1px $strong-cyan;
  }

  input:checked + .switch-slider:before {
    -webkit-transform: translateX(26px);
    -ms-transform: translateX(26px);
    transform: translateX(26px);
  }

  /* Rounded sliders */
  .switch-slider.round {
    border-radius: 34px;
  }

  .switch-slider.round:before {
    border-radius: 50%;
  }
}

.discount {
  display: inline-block;
  background-color: $light-grayish-red;
  color: $light-red;
  border-radius: 20px;
  padding: 3px 8px;
  margin-left: rem(6px);

  > span {
    color: $light-red;

    @media(max-width: 1439px) {
      display: none;
    }
  }
}
</style>