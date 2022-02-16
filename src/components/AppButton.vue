<template>
    <button :style="styles" @mouseover="onMouseOver" @mouseout="onMouseOut"><slot/></button>
</template>
<script>
export default {
  name: 'AppButton',

  props: {
    cursor: {
      type: String,
      default: 'pointer'
    },
    border: {
      type: [Number, String],
      default: 1
    },
    borderColor: {
      type: String,
      default: '#0000'
    },
    disabled: {
      type: Boolean,
      default: false
    },
    disabledBorderColor: {
      type: String,
      default:  '#4A4651'
    },
    disableColor: {
      type: String,
      default: '#54505C'
    },
    disableBackground: {
      type: String,
      default: '#38353d'
    },
    background: {
      type: String,
      default: '#fef033'
    },
    color: {
      type: String,
      default: '#4D493E'
    },
    mouseoverColor: {
      type: String,
      default: '#4D493E'
    },
    mouseoverBackground: {
      type: String,
      default: '#fff68D'
    },
    padding: {
      type: [String, Number],
      default: '10px 35px'
    },
    margin: {
      type: [String, Number],
      default: '1'
    },
    radius: {
      type: [String, Number],
      default: 0
    }

  },

  data () {
    return  {
      isMouseOver: false
    }
  },

  computed: {
    styles () {
      return {
        borderWidth: this.getBorder,
        borderColor: this.getBorderColor,
        background: this.getBackground,
        color: this.getColor,
        cursor: this.getCursor,
        padding: this.getPadding,
        margin: this.getMargin,
        borderRadius: this.getBorderRadius
      }
    },
    getCursor () {
      return this.disabled ? 'not-allowed' : this.cursor
    },
    getBorder () {
      if(this.isNumber(this.border)){
        return this.border + 'px'
      }
      return this.border
    },
    getBorderColor () {
      if(this.disabled)
        return this.disabledBorderColor
      return this.borderColor
    },
    getBackground () {
      if(this.disabled)
        return this.disableBackground

      if(this.isMouseOver)
        return this.mouseoverBackground
      return this.background
    },
    getColor () {
      if(this.disabled)
        return this.disableColor

      if(this.isMouseOver)
        return this.mouseoverColor
      return this.color
    },
    getPadding () {
      if(this.isNumber(this.padding))
        return this.padding + 'px'
      return this.padding
    },
    getMargin () {
      if(this.isNumber(this.margin))
        return this.margin + 'px'
      return this.margin
    },
    getBorderRadius () {
      if(this.isNumber(this.radius))
        return this.radius + 'px'
      return this.radius
    }
  },

  methods: {
    isNumber (value) {
      return /ˆ\d+$/.test(value)
    },
    onMouseOver () {
      this.isMouseOver= true
    },
    onMouseOut () {
      return this.isMouseOver = false
    }
  }

}

</script>
<style scoped>
  button {
    background-color: #4CAF50; /* Green */
    outline: none;
    border: solid;
    color: white;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 0 10px;
    cursor: pointer;
  }

</style>
