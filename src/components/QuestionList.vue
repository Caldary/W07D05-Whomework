<template lang="html">
  <div>
      <ul>
          <list-question v-for="(question, index) in questions" :question="question.question" :key="index"></list-question>
      </ul>
  </div>
</template>

<script>
import ListQuestion from './ListQuestion.vue';
import { eventBus } from '../main.js'

export default {
    name: 'question_list',
    props: ['questions'],
    components: {
        "list-question": ListQuestion
    }
}
</script>

<style>

</style>