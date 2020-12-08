<template>
  <section class="top">
    <div class="search">
      <input type="text" class="search-input" placeholder="Поиск по системе" />
      <button class="btn btn-search"></button>
    </div>
    <div class="profile">
      <img
        src="~/assets/img/profile.jpg"
        alt="profile-img"
        class="profile__img"
      />
      <div>
        <p class="profile__name">
          Alexander C.
        </p>
        <p class="profile__position">Администратор</p>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "top",
};
</script>
<style lang="scss" scoped>
.top {
  height: 150px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.search {
  width: 60%;
  position: relative;
  &-input {
    width: 100%;
    padding: 13px 0 13px 15px;
    border-radius: 5px;
    font-size: 16px;
    border: 3px solid #f8f8f8;
    outline: none;
  }
}
.profile {
  display: flex;
  align-items: center;
  &__img {
    width: 60px;
    height: 60px;
    border-radius: 50px;
    margin-right: 5px;
  }
  &__name {
    font-size: 20px;
    font-weight: bold;
  }
  &__position {
    color: #b6b6b6;
    font-size: 16px;
  }
}
.btn-search {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  &:before {
    content: url("~assets/img/search.svg");
  }
}
</style>
