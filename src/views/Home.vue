<template>
  <div class="home">
    <Button @clicked="clicked"
      :text="worldText"/>

    <div v-show="showWorld">
      <img alt="Vue logo" src="../assets/logo.png">
      <HelloWorld msg="Welcome to Your Vue.js + TypeScript App"/>
    </div>

    <br/><br/>
    <Button v-show="!showWorld && !squares"
      @click="$router.push('squares')"
      text="squares"/>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import HelloWorld from '@/components/HelloWorld.vue' // @ is an alias to /src
import Button from '@/components/Button.vue'

export default defineComponent({
  name: 'Home',
  components: {
    HelloWorld,
    Button
  },
  data () {
    return {
      showWorld: false,
      worldText: 'show welcome info'
    }
  },
  methods: {
    clicked () {
      this.showWorld = !this.showWorld
      this.worldText.includes('show') ? this.worldText = 'hide welcome info' : this.worldText = 'show welcome info'
    }
  }
})
</script>
