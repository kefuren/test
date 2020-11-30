<template>
  <div class="row" style="height: 100%; width: 100%">
    <div class="relative-position line-k" style="width: 220px; height: 100vh">
      <q-Left :list="essentialLinks" />
    </div>

    <!-- 动态组件 is -->
    <div style="flex:1"><div :is="crurentPage"></div></div>
  </div>
</template>

<script>
const files = require.context("./center", false, /\.vue$/);

const components = {};
// 遍历files对象，构建components键值
files.keys().forEach((key) => {
  components[key.replace(/(\.\/|\.vue)/g, "")] = files(key).default;
});

const linksData = [
  {
    title: "商家通告",
    icon: "school",
    link: "q-Notice",
  },
  {
    title: "发布任务",
    icon: "code",
    link: "q-PublishTask",
  },
  {
    title: "店铺管理",
    icon: "chat",
    link: "q-StoreManagement",
  },
  {
    title: "垫付任务管理",
    icon: "record_voice_over",
    link: "q-AdvanceTaskManagement",
  },
  {
    title: "浏览任务管理",
    icon: "rss_feed",
    link: "",
  },
  {
    title: "代接订单",
    icon: "public",
    link: "",
  },
  {
    title: "资金明细",
    icon: "favorite",
    link: "",
  },
];

export default {
  name: "MainLayout",
  components,
  data() {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData,
      crurentPage: "q-Notice",
    };
  },

  mounted() {
    this.$root.$on("changeList", (e) => {
      this.crurentPage = e;
    });
  },

  beforeDestroy() {
    // Don't forget to turn the listener off before your component is destroyed
    this.$root.$off("changeList");
  },
};
</script>

<style lang="scss">
.line-k {
  border-right: solid 1px rgba(0, 0, 0, 0.12);
}
</style>