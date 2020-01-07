<template>
  <div id="app">
    <div v-for="(product, index) in products" :key="index">
      <AppInput
        :product="product"
        @onUpdate="update($event)"
      />
    </div>
    <hr/>
    {{ products }}
  </div>
</template>

<script>
import AppInput from './components/AppInput.vue'

export default {
  name: 'app',
  components: {
    AppInput
  },
  data () {
    return {
      products: [
        { name: 'Шар', value: 5 },
        { name: 'Цилиндр', value: 10 },
        { name: 'Куб', value: 15 }
      ]
    }
  },
  methods: {
    update (payload) {
      this.$set(payload.product, payload.prop, payload.newValue)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
