<template>
    <button @click="this.$emit('clicked')">{{text}}</button>
</template>

<script>
export default {
  name: 'Button',
  props: {
    text: String
  }
}
</script>

<style scoped>
    button {
        background-color:midnightblue;
        color:rgb(221, 238, 253);
        display: inline-block;
        border: none;
        padding: 10px 20px;
        margin: 5px;
        border-radius: 5px;
        cursor: pointer;
        text-decoration: none;
        font-size: 15px;
        font-family: inherit;
    }
</style>
