<template>
  <section>
    <div class="navigation">
      <button
        v-for="(button, index) in buttons"
        :key="index"
        class="btn btn-navigation"
        @click="setComponent(index, button)"
        :class="{ 'btn-active': clickedBtnIndex === index }"
      >
        {{ button.text }}
      </button>
      <keep-alive>
        <component :is="clickedBtnName" class="component" />
      </keep-alive>
    </div>
  </section>
</template>
<script>
export default {
  name: "polls",
  layout: "default",
  components: {
    params: () => import("~/components/Params.vue"),
    questions: () => import("~/components/Questions.vue"),
    logic: () => import("~/components/Logic.vue"),
    conditions: () => import("~/components/Conditions.vue"),
    respondents: () => import("~/components/Respondents.vue"),
  },
  data() {
    return {
      clickedBtnIndex: 4,
      clickedBtnName: "respondents",
      buttons: [
        { name: "params", text: "Параметры" },
        { name: "questions", text: "Вопросы" },
        { name: "logic", text: "Логика" },
        { name: "conditions", text: "Условия" },
        { name: "respondents", text: "Респонденты" },
      ],
    };
  },
  methods: {
    setComponent(index, button) {
      this.clickedBtnIndex = index;
      this.clickedBtnName = button.name;
    },
  },
};
</script>
<style lang="scss" scoped>
.navigation {
  margin-bottom: 80px;
}
.btn-navigation {
  color: #2f8a42;
  padding: 8px 16px;
  font-size: 18px;
  font-weight: bold;
  margin-left: 10px;
  margin-right: 10px;
  border-bottom: 4px solid transparent;
  &:first-child {
    margin-left: 0;
  }
  &:hover {
    background-color: #f8f8f8;
  }
}
.btn-active {
  border-bottom: 4px solid #dbf28b;
  color: #000000;
}
</style>
