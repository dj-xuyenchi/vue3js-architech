<template>
  <NavsBar />
  <HeaderAdmin />
  <div id="admin-body">
    <router-view />
  </div>
</template>

<script>
import NavsBar from "./NavsBar.vue";
import HeaderAdmin from "./HeaderAdmin.vue";
export default {
  name: "AdminLayout",
  components: { NavsBar, HeaderAdmin },
};
</script>

<style lang="css" scoped>
#admin-body {
  margin-left: 18.75%;
  width: 80%;
  margin-top: 104px;
  min-height: 100vh;
}
</style>
