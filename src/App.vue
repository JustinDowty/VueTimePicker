<template>
  <div id="app">
    {{timeVal}}<br><br>
    <TimePicker v-model="timeVal"></TimePicker>
  </div>
</template>

<script>
import TimePicker from './TimePicker'

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
    
  }
}
</script>

<style>
  #app { margin: 50px 0 0 50px; }
</style>
