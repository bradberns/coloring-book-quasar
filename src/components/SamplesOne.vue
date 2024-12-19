<script setup>
import { ref } from "vue";

const alert = ref(false);
const slide = ref(1);
const autoplay = ref(true);
</script>

<template>
  <div class="q-mx-auto text-center q-my-sm">
    <q-btn label="Coloring Book - Samples" size="12px" outline color="primary" @click="alert = true" />
  </div>
  <q-dialog v-model="alert">
    <q-card class="w-full">
      <q-carousel animated v-model="slide" ref="carousel" swipeable navigation infinite :autoplay="autoplay">
        <q-carousel-slide :name="1"
          img-src="https://res.cloudinary.com/dxbedpcbe/image/upload/b_rgb:C2C9D6/c_pad,w_400,h_300,ar_4:3/v1732049349/16_tugsdj.png" />
        <q-carousel-slide :name="2"
          img-src="https://res.cloudinary.com/dxbedpcbe/image/upload/b_rgb:C2C9D6/c_pad,w_400,h_300,ar_4:3/v1732052998/20_kpxvd9.png" />
        <q-carousel-slide :name="3"
          img-src="https://res.cloudinary.com/dxbedpcbe/image/upload/b_rgb:C2C9D6/c_pad,w_400,h_300,ar_4:3/v1732052999/21_dyqpff.png" />

        <template v-slot:control>
          <q-carousel-control position="bottom-right" :offset="[18, 18]" class="q-gutter-xs">
            <q-btn push round dense color="orange" text-color="black" icon="arrow_left"
              @click="$refs.carousel.previous()" />
            <q-btn push round dense color="orange" text-color="black" icon="arrow_right"
              @click="$refs.carousel.next()" />
          </q-carousel-control>
        </template>
      </q-carousel>
    </q-card>
  </q-dialog>
</template>
