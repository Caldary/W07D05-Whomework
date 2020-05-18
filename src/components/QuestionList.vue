<template lang="html">
  <div>
      <ul>
          <list-question v-for="(question, index) in questions" :question="question.question" :key="index"></list-question>
      </ul>
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'question-list',
    props: ['questions']
  
}
</script>

<style>

</style>