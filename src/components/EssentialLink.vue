<template>
  <q-item
    class="bg-[#9c27b0] text-white border-b border-neutral-50 mb-0.5"
    clickable
    tag="a"
    target="_blank"
    :href="props.link"
  >
    <q-item-section v-if="props.icon" avatar>
      <q-icon :name="props.icon" />
    </q-item-section>

    <q-item-section class="text-lg lg:text-base">
      <q-item-label>{{ props.title }}</q-item-label>
      <q-item-label class="text-white" caption>{{ props.caption }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    required: true,
  },

  caption: {
    type: String,
    default: "",
  },

  link: {
    type: String,
    default: "#",
  },

  icon: {
    type: String,
    default: "",
  },
});
</script>
