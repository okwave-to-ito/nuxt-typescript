<template>
  <div>
    <div v-for="question in questions" :key="question.question_id" class="question_element">
      <question-list-element
        :question="question"
      ></question-list-element>
    </div>
  </div>
</template>

<script lang="ts">
import Vue , { PropOptions } from "vue"
import QuestionListElement, { Question } from "~/components/Question.vue"

export default Vue.extend({
  name: "QuestionList",

  components: {
    QuestionListElement
  },

  props: {
    questions: {
      type: Array,
      required: true
    } as PropOptions<Array<Question>>
  }
})
</script>

<style scoped>
.question_element {
  margin: 16px 16px 0px 32px;
}
</style>
