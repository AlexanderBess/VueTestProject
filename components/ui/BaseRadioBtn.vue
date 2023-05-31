<template>
  <label class="radio-btn">
    {{label}}
    <input
      class="radio-btn__checkbox"
      type="radio"
      :checked="isChecked"
      :value="value"
      @change="$emit('change', $event.target.value)" />
    <span class="radio-btn__checkmark"/>
  </label>
</template>

<script>
export default {
  name: "BaseRadioBtn",
  model: {
    prop: 'modelValue',
    event: 'change'
  },
  props: {
    label: {
      type: String,
      default: "",
      required:true
    },
    modelValue: {
      default: ""
    },
    "value": {
      type: String,
      default: undefined
    }
  },
  computed: {
    isChecked() {
      return this.modelValue === this.value
    }
  }
}
</script>

<style lang="scss" scoped>
.radio-btn {
  display: block;
  position: relative;
  width: 100%;
  padding-left: 35px;
  margin-bottom: 6px;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;

  font-weight: 400;
  font-size: 16px;
  line-height: 20px;
  &__checkbox {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    height: 0;
    width: 0;
  }
  &__checkmark {
    position: absolute;
    top: 0;
    left: 0;
    height: 20px;
    width: 20px;
    background: $black1;
    box-shadow: 2px 2px 5px rgba(8, 7, 13, 0.42), inset 1px 1px 3px rgba(77, 85, 99, 0.52);
    border-radius: 50px;
  }
  &__checkmark:after {
    content: "";
    position: absolute;
    left: 35%;
    right: 35%;
    top: 35%;
    bottom: 35%;
    border-radius: 50%;
    background: #717580;
  }
  &__checkbox:checked ~ .radio-btn__checkmark {
    background: linear-gradient(90deg, #7930DE 0%, #7F65FF 100%);
    box-shadow: 2px 2px 5px rgba(31, 36, 47, 0.5), inset 1px 1px 2px rgba(8, 7, 13, 0.24);
    border-radius: 50px;
  }
  &__checkbox:checked ~ .radio-btn__checkmark:after {
    display: block;
    background: #363A42;
  }
}
</style>
