<template>
  <div>
    <template v-for="item in list">
      <q-item
        :key="item.link"
        clickable
        :href="item.link"
        :active="item.link === currentModule"
        active-class="my-menu-link"
        @click="setActive(item)"
      >
        <q-item-section v-if="item.icon" avatar>
          <q-icon :name="item.icon" />
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ item.title }}</q-item-label>
        </q-item-section>
      </q-item>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    list: {
      type: Array,
      default: () => {},
    },
  },

  data() {
    return {
      currentModule: "q-Notice",
    };
  },
  methods: {
    setActive(item) {
      this.currentModule = item.link;
      this.$root.$emit("changeList", item.link);
    },
  },
};
</script>

<style lang="scss">
.my-menu-link {
  background: rgb(230, 237, 245);
}
</style>