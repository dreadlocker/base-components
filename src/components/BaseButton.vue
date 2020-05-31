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
      default: "BUTTON",
      validator: (val) => (/^[A-Za-z0-9]{1,30}$/g).test(val)
    },
    onClick: {
      type: Function,
    },
    type: {
      type: String,
      default: "button",
      validator: (val) => (/^button$|^submit$|^reset$/g).test(val)
    },
    classes: {
      type: String,
    },
    disabled: {
      type: Boolean,
      default: false,
      validator: (val) => (/^false$|^true$/g).test(val)
    },
    autofocus: {
      type: Boolean,
      default: false,
      validator: (val) => (/^false$|^true$/g).test(val)
    },
    name: {
      type: String,
      validator: (val) => (/^[A-Za-z0-9]{1,30}$/g).test(val)
    },
    value: {
      type: String,
      validator: (val) => (/^[A-Za-z0-9]{1,30}$/g).test(val)
    },
    // If the button belongs to a <form> use it's ID
    formId: {
      type: String,
      validator: (val) => (/^[A-Za-z0-9]{1,30}$/g).test(val)
    },
    // where to send the form-data
    formactionUrl: {
      type: String,
    },
    // how form-data should be encoded
    formenctype: {
      type: String,
      validator: (val) => (/^application\/x-www-form-urlencoded$|^multipart\/form-data$|^text\/plain$/g).test(val)
    },
    formmethod: {
      type: String,
      validator: (val) => (/^get$|^post$/g).test(val)
    },
    // form-data should NOT be validated on submission
    formnovalidate: {
      type: Boolean,
      default: false,
      validator: (val) => (/^false$|^true$/g).test(val)
    },
    // where to display the response after submitting the form(_blank)
    formtarget: {
      type: String,
      validator: (val) => (/^_blank$|^_self$|^_parent$|^_top$|^framename$/g).test(val)
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
