<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-btn flat dense icon="menu" aria-label="Menu" @click="toggleLeftDrawer" />
        <!-- <q-avatar>
          <img src="https://res.cloudinary.com/dxbedpcbe/image/upload/v1734036932/piclumen-1733444559356_ypdjfy.png"
            font-size="52px" size="300">
        </q-avatar> -->
        <q-toolbar-title class="text-center"> Brad's Beauties </q-toolbar-title>

        <div>v2.1.0</div>
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" bordered>
      <q-list>
        <q-item-label header class="bg-accent text-center text-white text-bold">
          Other Projects
        </q-item-label>

        <EssentialLink v-for="link in linksList" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer elevated class="bg-primary text-white">
      <div class="text-h5 text-center q-my-sm">Copyright 2024</div>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import EssentialLink from "components/EssentialLink.vue";

const linksList = [
  {
    title: "Brad Berns",
    caption: "personal website",
    icon: "",
    link: "https://bradberns.netlify.app/",
  },
  {
    title: "Onlyfans",
    caption: "onlyfans.com/bradberns",
    icon: "",
    link: "https://onlyfans.com/bradberns",
  },
  {
    title: "ManyVids",
    caption: "BradBernsxxx.manyvids.com",
    icon: "",
    link: "https://BradBernsxxx.manyvids.com",
  },
  {
    title: "LoyalFans",
    caption: "loyalfans.com/bradbernsxxx",
    icon: "",
    link: "https://www.loyalfans.com/bradbernsxxx",
  },
  {
    title: "Twitter",
    caption: "@BradBernsxx",
    icon: "",
    link: "https://x.com/BradBernsXX",
  },
  {
    title: "Reddit",
    caption: "Brad Bernsxxx",
    icon: "",
    link: "https://www.reddit.com/u/Bradbernsxxx",
  },
  // {
  //   title: 'Quasar Awesome',
  //   caption: 'Community Quasar projects',
  //   icon: 'favorite',
  //   link: 'https://awesome.quasar.dev'
  // }
];

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>
