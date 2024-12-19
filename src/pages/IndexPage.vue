<script setup>
import { ref } from "vue";
//import ContactComponent from "src/components/ContactComponent.vue";
import SamplesOne from "src/components/SamplesOne.vue";
import SamplesTwo from "src/components/SamplesTwo.vue";
import SamplesThree from "src/components/SamplesThree.vue";
//

const showing = ref(true);

setTimeout(() => {
  showing.value = false;
}, 1500);
</script>

<template>
  <q-page>
    <div class="my-2 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
      <div id="img" class="mx-auto w-full p-2 lg:p-0 bg-gray-200 md:bg-gray-50">
        <q-card>
          <img alt="Brad BernsXXX" class="mx-auto p-1 rounded-xl"
            src="https://res.cloudinary.com/dxbedpcbe/image/upload/v1732139973/brad_berns-2_pywfds.png" width="300"
            height="300" />
          <q-inner-loading :showing="showing" size="50px" color="primary" label="Please wait..."
            label-class="text-primary" label-style="font-size: 2.1em" transition-show="scale" transition-hide="scale" />
        </q-card>
      </div>
      <div id="intro" class="mx-auto">
        <div class="text-left px-2">
          <h1 class="text-2xl text-center">Welcome to Brad's Beauties</h1>
          <p class="mt-2 indent-1.5 text-lg lg:text-base">
            Here you'll find AI created sketches of pretty women, perfect for coloring.
            Each zip file has over 20 images and each image is 1148 px (height) and 896 px
            (width). Feel free to download the complete zip files, or one of the samples
            below.
          </p>
          <ul id="zip_files" class="mt-2 text-lg lg:text-base mx-24 lg:mx-0">
            <li class="my-2">
              <a class="hover:underline p-1 text-blue-500 font-medium"
                href="https://www.dropbox.com/scl/fi/ngfsxizqnqo5ttpinwv91/coloringbook.zip?rlkey=i1s4u539vdzstatbpht1ldj7e&st=u16xtq3y&dl=0">
                ColoringBook.zip
              </a>
              <span class="font-light italic">(Original)</span>
            </li>
            <li class="my-2">
              <a class="hover:underline p-1 text-blue-500 font-medium"
                href="https://www.dropbox.com/scl/fi/2re8a7o4xz96gqgsi02fr/coloringbook-2.zip?rlkey=xbg1sa6d3xrryh0vhke1rhdb6&st=ikxq8c0j&dl=0">
                ColoringBook-2.zip
                <br class="lg:hidden" />
              </a>
              <span class="font-light italic">(nurses, cowgirls,...)</span>
            </li>
            <li class="my-2">
              <a class="hover:underline p-1 text-blue-500 font-medium"
                href="https://www.dropbox.com/scl/fi/7wabxlucfcqd10qf3zs0h/coloringbook-3.zip?rlkey=p0dgyxv4rs9w6siifcgfxrilg&st=wk39z7nq&dl=0">
                ColoringBook-3.zip
                <br class="lg:hidden" />
              </a>
              <span class="font-light italic">(various anime girls)</span>
            </li>
          </ul>
        </div>
        <div id="sample_btns" class="mt-3 text-center">
          <!-- <ContactComponent /> -->
          <SamplesOne />
          <SamplesTwo />

          <SamplesThree />
        </div>
      </div>
      <div id="vid" class="mx-auto w-full p-2 lg:-mt-3 bg-gray-200 md:bg-gray-50">
        <video controls loop="true" class="p-2 bg-transparent lg:w-4/5 w-full rounded-lg mx-auto">
          <source src="https://res.cloudinary.com/dxbedpcbe/video/upload/v1732989824/Angel_vid_latest_yw5oha.mp4"
            type="video/webm" />
          Your browser does not support the video.
        </video>
      </div>
    </div>
  </q-page>
</template>
