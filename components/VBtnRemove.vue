<template>
  <button class="btn v-btn-remove">Удалить условие</button>
</template>
<script>
export default {
  name: "v-btn-remove",
};
</script>
<style lang="scss" scoped>
.v-btn-remove {
  margin: 1px;
  position: relative;
  padding: 10px 12px;
  color: #ff1203;
  border: 1px solid #fdd1d1;
  border-radius: 5px;
  font-size: 16px;
  display: flex;
  align-items: center;
  background-color: #ffffff;
  align-self: flex-end;
  &:before {
    content: url("~assets/img/trash.svg");
    margin-right: 10px;
  }
  &:hover {
    background-color: #ffe4e4;
  }
}
</style>
