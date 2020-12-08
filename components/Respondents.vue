<template>
  <section>
    <p class="title">Добавить опрос</p>
    <section class="form-condition condition-1">
      <div class="condition">
        <p class="condition-title condition-title-1">Условие 1</p>
        <v-autocomplete :items="items" v-model="conditionTitle" />
      </div>
      <div class="condition-params-respondent-age">
        <div class="row">
          <div class="range">
            <span class="age-range">Диапазон 1</span>
          </div>
          <label> от <input type="text" class="input-age" /> </label>
          <label> до <input type="text" class="input-age" /> </label>
        </div>
        <div class="row">
          <div class="range">
            <span class="another-params">или</span>
            <span class="age-range">Диапазон 2</span>
          </div>
          <label> от <input type="text" class="input-age" /> </label>
          <label> до <input type="text" class="input-age" /> </label>
        </div>
        <div class="buttons">
          <button class="btn btn-add">+ Добавить диапазон</button>
          <v-btn-remove />
        </div>
      </div>
    </section>
    <section class="form-condition  condition-2">
      <div class="block-and block-and-2">И</div>
      <div class="condition">
        <p class="condition-title condition-title-2">Условие 2</p>
        <v-autocomplete :items="items" v-model="conditionTitle" />
      </div>
      <div class="type">
        <span class="range ">Тип 1</span>
        <v-autocomplete :items="typesCard" v-model="defaultType" />
      </div>
      <div class="buttons">
        <button class="btn btn-add">+ Добавить тип</button>
        <v-btn-remove />
      </div>
    </section>
    <section class="form-condition  condition-3">
      <div class="block-and block-and-3">И</div>
      <div class="condition">
        <p class="condition-title condition-title-3">Условие 3</p>
        <v-autocomplete :items="items" v-model="conditionTitle" />
      </div>
      <div class="status">
        <span class="range ">Статус 1</span>
        <v-autocomplete :items="statusCards" v-model="defaultStatus" />
      </div>
      <div class="buttons">
        <button class="btn btn-add">+ Добавить статус</button>
        <v-btn-remove />
      </div>
    </section>
    <section class="form-condition  condition-4">
      <div class="condition">
        <p class="condition-title condition-title-5">Условие 4</p>
        <v-autocomplete :items="items" v-model="conditionTitle" />
      </div>
      <v-btn-remove />
    </section>
    <section class="form-add-condition">
      <div class="form-add-condition__description">
        <p class="form-add-condition__plus">+</p>
        <p>Нажмите чтобы добавить новое условие выборки</p>
        <p>Все условия связываются между собой логическим "И"</p>
      </div>
    </section>
    <section class="component__bottom">
      <button class="btn btn-test">Протестировать опрос</button>
      <button class="btn btn-next">Далее</button>
    </section>
  </section>
</template>
<script>
import VBtnRemove from "./VBtnRemove.vue";
export default {
  name: "respondents",
  components: {
    "v-autocomplete": () => import("~/components/VAutocomplete.vue"),
    "v-btn-remove": () => import("~/components/VBtnRemove.vue"),
  },
  data() {
    return {
      items: [
        { title: "Статус карты лояльности", value: "cardStatus" },
        { title: "Тип карты лояльности", value: "cardType" },
        { title: "Возраст респондента", value: "userAge" },
      ],
      typesCard: [
        { title: "Gold", value: "gold" },
        { title: "Platinum", value: "platinum" },
        { title: "Diamond", value: "diamond" },
      ],
      statusCards: [
        { title: "Активна", value: "active" },
        { title: "Заблокирована", value: "blocked" },
        { title: "Перевыпускается", value: "refresh" },
      ],
      defaultStatus: "Активна",
      defaultType: "Gold",
      conditionTitle: "Выберите условие",
    };
  },
};
</script>
<style lang="scss" scoped>
.btn {
  &-test,
  &-next {
    padding: 10px 12px;
    border-radius: 5px;
    font-size: 16px;
  }
  &-test {
    background-color: #ffffff;
    color: #34b44e;
  }
  &-next {
    background-color: #06a326;
    color: #ffffff;
    position: relative;
    padding-right: 26px;
    &:after {
      position: absolute;
      content: url("~assets/img/arrow.svg");
      margin-left: 5px;
    }
  }
}
.form {
  &-condition {
    padding: 10px 26px;
    position: relative;
    display: flex;
    flex-direction: column;
  }
  &-add-condition {
    padding: 30px;
    &__description {
      cursor: pointer;
      font-size: 16px;
      padding: 10px;
      border: 4px solid #f4f7f9;
      border-radius: 8px;
      color: #2f8a42;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    &__plus {
      font-size: 40px;
    }
  }
}
.block-and {
  &-2 {
    background-color: #e5f0fa;
  }
  &-3 {
    background-color: #e7f6db;
  }
  &-2,
  &-3 {
    padding: 15px 22px;
    position: absolute;
    border-radius: 8px;
    top: -28px;
    left: 40px;
  }
}
.condition {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 30px;
  &-title {
    font-size: 20px;
    &-1 {
      color: #ac8019;
      font-weight: bold;
    }
    &-2 {
      color: #4162b3;
      font-weight: bold;
    }
    &-3 {
      color: #75ab2e;
      font-weight: bold;
    }
    &-4 {
      color: #000000;
      font-weight: bold;
    }
  }
  &-1 {
    background-color: #fffcf5;
  }
  &-2 {
    background-color: #f8faff;
  }
  &-3 {
    background-color: #fafff8;
  }
  &-4 {
    background-color: #f4f7f9;
  }
  &-params-respondent-age {
    display: flex;
    flex-direction: column;
  }
}
.row {
  margin-bottom: 20px;
  font-size: 20px;
  display: flex;
  align-items: baseline;

  & > :nth-child(2) {
    margin-right: 5px;
  }
}
.range {
  width: 30%;
  font-size: 20px;
}
.type,
.status {
  display: flex;
  align-items: baseline;
  margin-bottom: 20px;
  & > :nth-child(2) {
    width: 50%;
  }
}
.buttons {
  width: 70%;
  align-self: flex-end;
  display: flex;
  justify-content: space-between;
  margin-top: 20px;
}
.btn-add {
  padding: 10px 12px;
  color: #dff399;
  border: 1px solid #edffaa;
  background-color: #ffffff;
  border-radius: 5px;
  font-size: 16px;
  &:hover {
    background-color: #f8ffd6;
  }
}
.another-params {
  border-radius: 8px;
  padding: 10px;
  background-color: #f7f1e3;
  margin-right: 5px;
}
.input-age {
  width: 24px;
  padding: 14px;
  font-size: 20px;
  outline: none;
  border: 2px solid #f8f8f8;
  border-radius: 5px;
}
</style>
