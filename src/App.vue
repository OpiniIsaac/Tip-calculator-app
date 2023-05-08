<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  {{ cart }}
<HelloWorld @add-to-cart="addToCart"/>
</template>
<script>
export default {
  data() {
    return {
      message: 'Hello, world!',
      cart:0
    }
  },
  methods:{
    addToCart(){
this.cart ++
    }
  }
}
</script>
<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
