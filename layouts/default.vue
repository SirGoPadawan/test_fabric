<template>
  <section class="container">
    <navmenu />
    <div class="content">
      <top />
      <Nuxt />
    </div>
  </section>
</template>
<script>
export default {
  components: {
    top: () => import("~/components/Top.vue"),
    navmenu: () => import("~/components/Nav.vue"),
  },
};
</script>
<style>
.container {
  max-width: 1366px;
  margin: 0 auto;
  padding-left: 18px;
  padding-right: 18px;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
}
.content {
  width: 82%;
  display: flex;
  flex-direction: column;
  padding-left: 59px;
  padding-right: 87px;
}
</style>
