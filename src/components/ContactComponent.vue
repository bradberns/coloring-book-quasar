<script>
import { ref } from 'vue'
const WEB3FORMS_ACCESS_KEY = "d300a0c4-7943-4850-8a9e-7ead4627c05d";

export default {
  setup() {
    const name = ref(null)
    const email = ref(null)
    const subject = "New Message from Coloring Book"
    const message = ref(null)

    return {
      alert: ref(false),
      name,
      email,
      subject,
      message,

      onSubmit() {
        const response = fetch("https://api.web3forms.com/submit", {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
            Accept: "application/json",
          },
          body: JSON.stringify({
            access_key: WEB3FORMS_ACCESS_KEY,
            name: this.name,
            subject: this.subject,
            email: this.email,
            message: this.message,
          }),
        });
        const result = response.json();
        if (result.success) {
          //console.log(result);
          this.name = "";
          this.email = "";
          this.message = "";
          // this.display = !this.display;
        }
      },
      onReset() {
        name.value = null
        email.value = null
        message.value = false
      }
    };
  },
  // methods: {

  //   async submitForm() {
  //     const response = await fetch("https://api.web3forms.com/submit", {
  //       method: "POST",
  //       headers: {
  //         "Content-Type": "application/json",
  //         Accept: "application/json",
  //       },
  //       body: JSON.stringify({
  //         access_key: WEB3FORMS_ACCESS_KEY,
  //         name: this.name,
  //         subject: this.subject,
  //         email: this.email,
  //         message: this.message,
  //       }),
  //     });
  //     const result = await response.json();
  //     if (result.success) {
  //       //console.log(result);
  //       this.name = "";
  //       this.email = "";
  //       this.message = "";
  //       // this.display = !this.display;
  //     }
  //   },
  // },
};
</script>

<template>
  <!-- <div class="q-mx-auto text-center q-my-sm">
    <q-btn label="Contact Me" size="15px" outline color="accent" @click="alert = true" />
  </div> -->

  <q-dialog v-model="alert">
    <q-card>
      <q-card-section class="text-center">
        <div class=" text-lg">Contact Me</div>
      </q-card-section>

      <q-card-section class="q-pt-none">
        <q-form @submit="onSubmit" @reset="onReset" style="width: 375px">
          <q-input dense v-model="name" hint="name" />
          <q-input dense v-model="email" hint="email" />
          <q-input dense v-model="message" type="textarea" hint="message" />
        </q-form>
      </q-card-section>

      <q-card-actions align="center">
        <q-btn size="15px" outline label="Cancel" color="negative" v-close-popup />
        <q-btn size="15px" outline label="Reset" type="reset" color="warning" />
        <q-btn size="15px" outline type="submit" label="Send" color="primary" />
      </q-card-actions>
    </q-card>
  </q-dialog>
</template>
