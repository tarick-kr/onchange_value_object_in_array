<template>
  <label>
    <span>{{ product.name }}</span>
    <input
      type="text"
      :value="this.product.value"
      @input="onChangeValue($event)"
    >
  </label>
</template>

<script>
export default {
  name: 'AppInput',
  props: ['product'],
  methods: {
    onChangeValue (e) {
      this.$emit('onUpdate', {
        product: this.product,
        prop: 'value',
        newValue: e.target.value
      })
    }
  }
}
</script>

<style scoped>
  input {
    margin-bottom: 25px;
  }
  span {
    display: block;
    margin-bottom: 5px;
  }
</style>
