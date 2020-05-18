<template lang="html">
  <div>
      <button v-on:click="selectAnswer">Select Answer</button>
  </div>
</template>

<script>
import { eventBus } form '../main.js';

export default {
    name: "select-answer",
    props: ["selectedAnswer"],
    
    methods: {
        selectAnswer: function() {
            eventBus.$emit("answer-selected", this.selectedAnswer)
        }
    }
}
</script>

<style>

</style>