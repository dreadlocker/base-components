<template>
  <button
    :type="type"
    :classes="classes"
    :disabled="disabled"
    :name="name"
    :value="value"
    class="btn"
  ><slot></slot></button>
</template>

<script>
// How to use it:
// <BaseButton>{{'BUTTON'}}</BaseButton>
export default {
  name: 'BaseButton',
  props: {
    type: {
      type: String,
      default: "button",
      validator: (val) => (/^button$|^submit$|^reset$/g).test(val)
    },
    classes: {
      type: String,
    },
    name: {
      type: String,
      validator: (val) => (/^[A-Za-z0-9]{1,30}$/g).test(val)
    },
    value: {
      type: String,
      validator: (val) => (/^[A-Za-z0-9]{1,30}$/g).test(val)
    },
  }
}
</script>

<style lang="sass" scoped>
.btn
  padding: 5px 10px
  &:active
    transform: scale(1.1)
</style>
