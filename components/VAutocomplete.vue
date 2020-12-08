<template>
  <section class="v-autocomplete">
    <div
      tabindex="0"
      @click="activeBtn = !activeBtn"
      class="v-autocomplete-title"
      :class="[activeBtn ? 'btn-up' : 'btn-down']"
    >
      {{ title }}
    </div>
    <div v-if="activeBtn" class="v-autocomplete-list">
      <div
        v-for="item in items"
        :key="item.value"
        class="v-autocomplete-item"
        @click="setValue(item)"
      >
        {{ item.title }}
      </div>
    </div>
  </section>
</template>
<script>
export default {
  props: ["items", "value"],
  name: "v-autocomplete",
  data() {
    return {
      title: this.value,
      activeBtn: false,
      selectedElemValue: "",
    };
  },

  methods: {
    setValue({ title, value }) {
      this.selectedElemValue = value;
      this.title = title;
      this.activeBtn = false;
    },
  },
};
</script>
<style lang="scss" scoped>
.v-autocomplete {
  width: 70%;
  &-title {
    outline-color: #dbf28b;
    margin: 1px;
    border: 2px solid #f8f8f8;
    border-radius: 5px;
    padding: 13px 0px;
    padding-left: 10px;
    font-size: 18px;
    cursor: pointer;
    position: relative;
    background-color: #ffffff;
    &:hover {
      background-color: #dadada;
    }
  }
  &-list {
    background-color: #ffffff;
  }
  &-item {
    cursor: pointer;
    border-bottom: 1px solid#dadada;
    margin-bottom: 2px;
    font-size: 18px;
    padding: 15px 10px;
    &:hover {
      background-color: #dadada;
    }
    &:last-child {
      margin-bottom: 0;
      border-bottom: 1px solid transparent;
    }
  }
}
.btn {
  &-up,
  &-down {
    &:after {
      position: absolute;
      right: 20px;
    }
  }
  &-up {
    &:after {
      content: url("~assets/img/arrow-up.svg");
    }
  }
  &-down {
    &:after {
      content: url("~assets/img/arrow-down.svg");
    }
  }
}
</style>
