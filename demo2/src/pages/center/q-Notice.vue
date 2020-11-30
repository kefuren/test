<template>
  <div class="q-pa-md">
    <q-toolbar class="bg-primary text-white shadow-2" style="width: 100%">
      <q-toolbar-title class="text-weight-bolder">今日必读</q-toolbar-title>
    </q-toolbar>

    <div style="">
      <q-tabs
        v-model="tab"
        dense
        align="left"
        class="text-primary shadow-2"
        :breakpoint="0"
      >
        <q-tab name="mails" label="商家公告" />
        <q-tab name="alarms" label="商家公告2" />
      </q-tabs>

      <q-list bordered>
        <q-item
          v-for="(contact, index) in contacts"
          :key="contact.id"
          class="q-my-sm"
          clickable
          v-ripple
          @click.stop="showNotice(contact)"
        >
          <q-item-section avatar>
            <q-avatar color="primary" size="md" text-color="white">
              {{ index + 1 }}
            </q-avatar>
          </q-item-section>

          <q-item-section>
            <q-item-label>{{ contact.name }}</q-item-label>
            <!-- <q-item-label caption lines="1">{{ contact.email }}</q-item-label> -->
          </q-item-section>

          <q-item-section side>
            {{ "2020/11/29" }}
          </q-item-section>
        </q-item>
      </q-list>
    </div>

    <q-dialog v-model="alert">
      <q-card>
        <q-card-section>
          <div class="text-h6">Alare</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum
          repellendus sit voluptate voluptas eveniet porro. Rerum blanditiis
          perferendis totam, ea at omnis vel numquam exercitationem aut, natus
          minima, porro labore.
        </q-card-section>

        <q-card-actions align="right">
          <q-btn flat label="OK" color="primary" v-close-popup />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
const contacts = [
  {
    id: 1,
    name: "可以大量放单啦！",
    email: "rjedrzej0@discuz.net",
    letter: "R",
  },
  {
    id: 2,
    name: "Mallorie Alessandrini",
    email: "malessandrini1@marketwatch.com",
    letter: "M",
  },
  {
    id: 3,
    name: "Elisabetta Wicklen",
    email: "ewicklen2@microsoft.com",
    letter: "E",
  },
  {
    id: 4,
    name: "Seka Fawdrey",
    email: "sfawdrey3@wired.com",
    letter: "S",
  },
];

const offline = [
  {
    id: 5,
    name: "Brunhilde Panswick",
    email: "bpanswick4@csmonitor.com",
    avatar: "avatar2.jpg",
  },
  {
    id: 6,
    name: "Winfield Stapforth",
    email: "wstapforth5@pcworld.com",
    avatar: "avatar6.jpg",
  },
];

export default {
  data() {
    return {
      tab: "mails",
      contacts,
      offline,
      alert: false,
      dialogData: {},
    };
  },
  methods: {
    showNotice(item) {
      this.alert = true;
    },
  },
};
</script>