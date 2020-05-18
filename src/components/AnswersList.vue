<template lang="html">
<div>
    <ul>
        <list-answer v-for="(answer, index) in questions" :correct_answer="answer.correct_answer" :incorrect_answers="answer.incorrect_answers"
    </ul>
</div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'answer_list',
    props: ['answers']
}
</script>



<style>

</style>