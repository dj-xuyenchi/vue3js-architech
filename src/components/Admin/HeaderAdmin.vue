<template>
  <v-card
    flat
    rounded="0"
    style="
      margin-left: 17.5%;
      height: 64px;
      box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
      position: fixed;
      top: 0;
      left: 0;
      width: 82.5%;
      z-index: 1;
    "
  >
    <v-toolbar prominent extended>
      <label style="margin: 0 20px 0 20px; font-size: 20px"> Dashboard </label>
      <v-menu>
        <template v-slot:activator="{ props: menu }">
          <v-tooltip location="top">
            <template v-slot:activator="{ props: tooltip }">
              <v-btn icon v-bind="mergeProps(menu, tooltip)" @click="goHome()">
                <v-icon>mdi mdi-home</v-icon>
              </v-btn>
            </template>
            <span>Về trang chủ</span>
          </v-tooltip>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-menu>
        <template v-slot:activator="{ props: menu }">
          <v-tooltip location="top">
            <template v-slot:activator="{ props: tooltip }">
              <v-btn icon v-bind="mergeProps(menu, tooltip)">
                <v-icon>mdi-magnify</v-icon>
              </v-btn>
            </template>
            <span>I'm A Tooltip</span>
          </v-tooltip>
        </template>
        <v-list>
          <v-list-item v-for="(item, index) in items" :key="index">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-spacer></v-spacer>
      <v-btn prepend-icon="mdi mdi-logout-variant" @click="logOut()">
        Log out
      </v-btn>
    </v-toolbar>
  </v-card>
</template>
<script>
import { mergeProps } from "vue";
export default {
  name: "HeaderAdmin",
  data: () => ({
    items: [
      { title: "Click Me1" },
      { title: "Click Me2" },
      { title: "Click Me3" },
      { title: "Click Me4" },
    ],
  }),
  methods: {
    mergeProps,
    logOut() {
      document.cookie = "token=;expires=Thu, 01 Jan 1970 00:00:01 GMT;";
      document.cookie = "refreshToken=;expires=Thu, 01 Jan 1970 00:00:01 GMT;";
      this.$router.push({ path: "/home/lobby" });
    },
    goHome() {
      this.$router.push({ path: "/home/lobby" });
    },
  },
};
</script>

<style lang="scss" scoped></style>
