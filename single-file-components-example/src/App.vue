<template>
  <div id="app">
    <section>
      <todo-counter v-bind:count="counter"></todo-counter>
      <ul>
          <todo-item task="Köp kaffe" v-bind:done="false" v-on:done="handleUpdate"></todo-item>
          <todo-item task="Köp kaka" v-bind:done="false" v-on:done="handleUpdate"></todo-item>
          <todo-item task="Brygg kaffe" v-bind:done="false" v-on:done="handleUpdate"></todo-item>
          <todo-item task="Drick kaffe" v-bind:done="false" v-on:done="handleUpdate"></todo-item>
      </ul>
    </section>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem';
import TodoCounter from './components/TodoCounter';

export default {
  name: 'App',
  components: {
    TodoItem,
    TodoCounter
  },
  data: function() {
    return {
      counter: 0
    }
  },
  methods: {
    handleUpdate: function() {
      this.counter = this.counter + 1;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
