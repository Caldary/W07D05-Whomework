<template>
<div>
  <li v-for="(question, index) in questions" :question="question" :key="index">{{question.question}}</li>
  <question-list :questions="questions"></question-list>
</div>
</template>



<script>

import { eventBus } from './main.js'
import QuestionList from "./components/QuestionList.vue"
import ListQuestion from "./components/ListQuestion"

export default {
  name: 'app',
  data(){
    return{
      questions: []
    }
  },
  mounted() {
    fetch('https://opentdb.com/api.php?amount=10')
    .then(res => res.json())
    .then(questions => this.questions = questions.results)
  },
  components: {
    "question-list": QuestionList,
    "list-question": ListQuestion
  }
}
</script>

<style>

</style>
