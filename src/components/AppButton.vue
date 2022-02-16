<template>
  <div>
    <button :style="{ backgroundColor: color,  width }" :class="`but ${theme}`">{{ text }}</button>
  </div>
</template>
<script>
export default {
  name: 'AppButton',

  data () {
    return {}
  },

  props: {
    text: {
      type: String,
      default: 'name'
    },

    color: {
      type: String,
    },

    width: {
      type: String,
      default: '20rem'
    },

    theme: {
      type: String,
      default: ''
    }
  }

}

</script>
<style>
  .but {
    font-size: 1.2rem;
    border: none;
    color: #656565;
    padding: 12px 40px;
    text-align: center;
    transition-duration: 0.2s;
    text-decoration: none;
    margin: 4px 2px;
    cursor: pointer;
    display: inline-block;
    text-transform: uppercase;
    border-radius: 10px;
    font-weight: bold;
  }
  .but:hover {
    background-color: rgba(255,255,255,0.3);
  }
  .but-disabled {
    opacity: 0.5;
    cursor: not-allowed;
    border: 1px solid #d4d4d4;
    color: #868686;
    z-index: -2;
  }

  .but-small {
    width: 10rem
  }
  .but-middle {
    width: 20rem;
  }
</style>
