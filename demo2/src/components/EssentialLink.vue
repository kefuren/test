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
  name: "EssentialLink",
  props: {
    list: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      currentModule: "https://quasar.dev",
    };
  },
  methods: {
    setActive(item) {
      this.currentModule = item.link;
    },
  },
};
</script>

<style lang="scss">
.my-menu-link {
  //   color: white;
  background: rgb(230, 237, 245);
  //   color: rgb(97, 97, 97);
}
</style>
