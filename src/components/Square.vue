<template>
    <button @click="changeColor" :style="{ background: color}"></button>
</template>

<script>
export default {
  name: 'Square',
  props: {
    selectedColor: String
  },
  data () {
    return {
      color: 'darkblue'
    }
  },
  methods: {
    changeColor () {
      this.color !== this.selectedColor ? this.color = this.selectedColor : this.color = 'white'
    }
  }
}
</script>

<style scoped>
    button {
        border: none;
        height: 50px;
        width: 50px;
        margin: 5px;
    }
</style>
