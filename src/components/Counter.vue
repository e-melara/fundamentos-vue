<template>
  <h1>{{ title || computedTitle }}</h1>
  <h3>{{ counter }}</h3>
  <div>
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
  </div>
</template>

<script>
export default {
  name: 'counter',
  props: {
    title: String,
    start: {
      type: Number,
      default: 0,
      required: true,
      validator: (value) => {
        return value > 100
      },
    },
  },
  data() {
    return {
      counter: 5,
    }
  },
  methods: {
    increment() {
      this.counter += 1
    },
    decrement() {
      this.counter -= 1
    },
  },
  computed: {
    computedTitle() {
      return 'Counter'
    },
  },
}
</script>

<style>
button {
  background-color: #64bb87;
  border: 1px solid white;
  color: white;
  cursor: pointer;
  margin: 0px 5px;
  padding: 5px 15px;
  transition: 0.3s ease-in-out;
}
</style>
