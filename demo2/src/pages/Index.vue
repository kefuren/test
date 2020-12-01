<template>
  <q-page class="">
    <q-tab-panels v-model="tab" animated>
      <q-tab-panel name="center">
        <Center />
      </q-tab-panel>

      <q-tab-panel name="alarms">
        <div class="text-h6">商家介绍</div>
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </q-tab-panel>

      <q-tab-panel name="movies">
        <div class="text-h6">常见问题</div>
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </q-tab-panel>
    </q-tab-panels>

    <q-page-sticky position="bottom-right" :offset="[18, 18]">
      <q-fab v-model="fab" color="accent" glossy icon="add" direction="up">
        <q-fab-action color="primary" icon="person_add">
          <q-tooltip
            anchor="center left"
            self="center right"
            :offset="[10, 10]"
          >
            <strong>商家客服</strong>
          </q-tooltip>
        </q-fab-action>
        <q-fab-action color="primary" icon="mail">
          <q-tooltip
            anchor="center left"
            self="center right"
            :offset="[10, 10]"
          >
            <strong>充值客服</strong>
          </q-tooltip>
        </q-fab-action>
      </q-fab>
    </q-page-sticky>
  </q-page>
</template>

<script>
import Center from "./Business";

export default {
  name: "PageIndex",

  components: { Center },

  data() {
    return {
      tab: "center",
      fab:true
    };
  },

  mounted() {
    this.$root.$on("change", (e) => {
      this.tab = e;
    });
  },

  beforeDestroy() {
    // Don't forget to turn the listener off before your component is destroyed
    this.$root.$off("change");
  },
};
</script>

<style lang="scss" scoped>
.q-tab-panel {
  padding: 0;
}
</style>
