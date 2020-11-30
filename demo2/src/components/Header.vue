<template>
  <q-header class="bg-grey-1" elevated style="">
    <div class="row justify-end" style="padding: 10px 12px; color: #999">
      <div class="hand-k">131****1111</div>
      <div class="hand-k">本金:0元 <span>充值</span></div>
      <div class="hand-k">退出</div>
      <div class="hand-k">修改密码</div>
    </div>

    <q-separator />

    <q-toolbar class="q-pa-md">
      <img
        class="logo"
        style="width: 200px; height: 100%"
        src="http://deepshu.com/v1/site/1022/logo3.png"
      />
      <q-space />
      <!-- <q-toolbar-title></q-toolbar-title> -->
      <div class="q-gutter-y-md">
        <q-tabs
          v-model="tab"
          dense
          class="text-grey"
          active-color="primary"
          indicator-color="primary"
          align="justify"
          narrow-indicator
          @click="changeTab(tab)"
        >
          <q-tab name="center" label="商家中心" />
          <q-tab name="alarms" label="商家介绍" />
          <q-tab name="movies" label="常见问题" />
        </q-tabs>
      </div>
    </q-toolbar>
  </q-header>
</template>

<script>
export default {
  data() {
    return {
      tab: "center",
      many:99.99
    };
  },

  methods: {
    changeTab(currentTab) {
      this.$root.$emit("change", currentTab);
    },
  },
};
</script>

<style lang="scss" scoped>
.q-separator--vertical {
  width: 1.5px;
  color: #ccc;
  margin: 8px 5px;
}
.hand-k {
  cursor: pointer;
}
</style>