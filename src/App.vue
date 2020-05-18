<template>
<div>
  <li v-for="(question, index) in questions" :question="question" :key="index">{{question.question}}{{question.incorrect_answers}}{{question.correct_answer}}</li>
  <question-list :questions="questions"></question-list>
</div>
</template>



<script>

import { eventBus } from './main.js'
import QuestionList from "./components/QuestionList.vue"
import AnswerList from "./components/AnswersList.vue"
import AnswerSelect from "./components/AnswerSelect.vue"


export default {
  name: 'app',
  data(){
    return{
      questions: [],
      answers: []
    }
  },
  mounted() {
    fetch('https://opentdb.com/api.php?amount=10')
    .then(res => res.json())
    .then(questions => this.questions = questions.results)
  },
  components: {
    "question-list": QuestionList,
    "answer-list": AnswerList
  }
}
</script>

<style>

</style>
