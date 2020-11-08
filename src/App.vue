<template>
  <div id="app">
    <NavBar></NavBar>
    <router-view />
  </div>
</template>

<script>
const NavBar = () => import("./components/dropdownmeun/NavBar");
export default {
  // name: "app",
  data() {
    return {};
  },
  components: {
    NavBar,
  },
};
</script>

<style lang="stylus" scoped></style>
<style>
</style>
