<template>
    <div class="squareText" :style="{ color: selectedColor }">Squares</div>
    <ColorSelector @selectColor="selectColor"/>
    <br/>
    <div v-for="i in 10" :key="i">
      <span v-for="i in 10" :key="i">
        <Square :selectedColor="selectedColor"/>
      </span>
    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import ColorSelector from '@/components/ColorSelector.vue'
import Square from '@/components/Square.vue'

export default defineComponent({
  name: 'Squares',
  components: {
    Square,
    ColorSelector
  },
  data () {
    return {
      selectedColor: 'darkblue'
    }
  },
  methods: {
    selectColor (selected: string) {
      this.selectedColor = selected
    }
  }
})
</script>

<style scoped>
    .squareText {
        font-family:inherit;
        font-size: 24pt;
    }
</style>
