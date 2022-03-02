<template>
    <span :key="c" v-for="(c, i) in colors">
      <button @click="selectColor(i)" :class="selected[i]" :style="{ background: c }"></button>
    </span>
</template>

<script>
export default {
  name: 'Square',
  data () {
    return {
      color: 'white',
      colors: ['darkblue', 'cornflowerblue', 'lightskyblue', 'lightseagreen', 'darkorange', 'sandybrown', 'blanchedalmond', 'khaki'],
      selected: ['selected', '', '', '', '', '', '', '']
    }
  },
  methods: {
    selectColor (pos) {
      this.color = this.colors[pos]
      this.selected = this.selected.map((_, i) => i === pos ? 'selected' : '')
      this.$emit('selectColor', this.color)
    }
  }
}
</script>

<style scoped>
    button {
        border: none;
        border-radius: 50%;
        height: 50px;
        width: 50px;
        margin: 10px;
    }

    .selected {
      border: 5px solid;
      border-color: #04AA6D;
    }
</style>
