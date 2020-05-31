<template>
  <button
    @click="onClick ? onClick() : null"
    :type="type"
    :classes="classes"
    :disabled="disabled"
    :autofocus="autofocus"
    :form="formId"
    :formactionUrl="formactionUrl"
    :formenctype="formenctype"
    :formmethod="formmethod"
    :formnovalidate="formnovalidate"
    :formtarget="formtarget"
    :name="name"
    :value="value"
    class="btn"
  >{{text}}</button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    text: {
      type: String,
      default: "Click me!",
    },
    onClick: {
      type: Function,
    },
    type: {
      type: String,
      default: "button",
    },
    classes: {
      type: String,
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    autofocus: {
      type: Boolean,
      default: false,
    },
    name: {
      type: String,
    },
    value: {
      type: String,
    },
    // If the button belongs to a <form> use it's ID
    formId: {
      type: String,
    },
    // where to send the form-data
    formactionUrl: {
      type: String,
    },
    // how form-data should be encoded
    formenctype: {
      type: String,
    },
    // get, post
    formmethod: {
      type: String,
    },
    // form-data should NOT be validated on submission
    formnovalidate: {
      type: Boolean,
      default: false,
    },
    // where to display the response after submitting the form(_blank)
    formtarget: {
      type: String,
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
