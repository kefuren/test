<template>
  <q-layout view="hHh lpR fFf">
    <Header />

    <!-- <EssentialLink :list="essentialLinks" /> -->

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";

import Header from "../components/Header";

const linksData = [
  {
    title: "商家通告",
    icon: "school",
    link: "https://quasar.dev",
  },
  {
    title: "发布任务",
    icon: "code",
    link: "https://github.com/quasarframework",
  },
  {
    title: "店铺管理",
    icon: "chat",
    link: "https://chat.quasar.dev",
  },
  {
    title: "垫付任务管理",
    icon: "record_voice_over",
    link: "https://forum.quasar.dev",
  },
  {
    title: "浏览任务管理",
    icon: "rss_feed",
    link: "https://twitter.quasar.dev",
  },
  {
    title: "代接订单",
    icon: "public",
    link: "https://facebook.quasar.dev",
  },
  {
    title: "资金明细",
    icon: "favorite",
    link: "https://awesome.quasar.dev",
  },
];

export default {
  name: "MainLayout",
  components: { EssentialLink, Header },
  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
    };
  },
};
</script>
