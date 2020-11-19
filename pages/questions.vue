<template>
  <main>
    <question-list
      :questions="mockData.questions"
    ></question-list>
  </main>
</template>

<script lang="ts">
import Vue from "vue"
import QuestionList from "~/components/Questions.vue"
import assetData from "~/data/questions.json"

export default Vue.extend({
  name: "Questions",

  components: {
    QuestionList
  },

  data() {
    return {
      mockData: assetData
    }
  }
})
</script>
