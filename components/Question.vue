<template>
  <section>
    <h3>{{ question.title }}</h3>
    <div>{{ question.body }}</div>
    <div>
      <span>{{ displayedNeedLevel }}</span>
      <span>{{ question.username }}</span>
      <span>{{ question.create_datetime }}</span>
      <span>[{{ question.category_name }}]</span>
    </div>
  </section>
</template>

<script lang="ts">
import Vue , { PropOptions } from "vue"

export type Question = {
  question_id: string,
  title: string,
  body: string,
  need_level: number,
  answer_count: number,
  is_supported: boolean,
  has_best_answer: boolean,
  is_closed: boolean,
  create_datetime: string,
  user_id: number,
  username: string,
  category_id: number,
  category_name: string
}

export default Vue.extend({
  name: "QuestionListElement",

  props: {
    question: {
      type: Object,
      required: true
    } as PropOptions<Question>
  },

  computed: {
    displayedNeedLevel(): string {
      let displayedNeedLevel = ""
      switch(this.question.need_level) {
        case 1:
          displayedNeedLevel = "すぐに回答を！"
          break
        case 2:
          displayedNeedLevel = "困ってます"
          break
        default:
          displayedNeedLevel = "暇なときにでも"
          break
      }
      return displayedNeedLevel
    }
  }
})
</script>

<style scoped>
span {
  font-size: 8px;
}
</style>
