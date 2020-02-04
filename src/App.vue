<template>
  <div id="app">
    {{timeVal}}<br><br>
    <TimePicker v-model="timeVal"></TimePicker>
  </div>
</template>

<script>
import TimePicker from './TimePicker.vue'

export default {
  name: 'app',
  components: {
    TimePicker
  },
  data() {
    return {
      timeVal: null
    }
  },
  methods: {
    update(value) {
      this.timeVal = value;
    }
  }
}
</script>

<style>
#app {
  margin: 60px;
}
</style>
