<template>
  <div class="flex items-center">
    <span>Monthly Billing</span>
    <div class="block">
      <label class="switch">
        <input type="checkbox">
        <span class="switch-slider round"></span>
      </label>
    </div>
    <span>
      Yearly Billing <span class="discount">-25%</span>
    </span>
  </div>
</template>

<script>
export default {
  name: 'SwitchComponent',
};
</script>

<style lang="scss">
@import '/src/assets/sass/_app';

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
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: $pale-blue;
    -webkit-transition: .4s;
    transition: .4s;
  }

  .switch-slider:before {
    position: absolute;
    content: "";
    height: 20px;
    width: 20px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    -webkit-transition: .4s;
    transition: .4s;
  }

  input:checked + .switch-slider {
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
  background-color: $light-grayish-red;
  color: $light-red;
  border-radius: 20px;
  padding: 3px 8px;
  margin-left: 4px;
}
</style>