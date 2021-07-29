<template>
  <div class="contact_page">
    <div id="title">
      <h1 class="contact_info">Get in touch</h1>
      <p class="contact_info info_text">
        Feel free to contact me, I will get back to you as soon as possible.
      </p>
    </div>
    <form action="" class="contact_info" autocomplete="off">
      <div class="input_box">
        <input
          type="text"
          name="name"
          v-model="form.name"
          required
          autocomplete="off"
        />
        <label for="name" class="label_name"> Name </label>
      </div>

      <div class="input_box">
        <input
          type="email"
          name="email"
          v-model="form.email"
          required
          autocomplete="off"
        />
        <label for="email"> Email </label>
      </div>

      <div class="input_box">
        <textarea
          v-model="form.message"
          name="message"
          required
          autocomplete="off"
        />
        <label for="message"> Message </label>
      </div>

      <BaseButton type="submit" @submit.prevent="sendForm"></BaseButton>
    </form>
  </div>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";
import { ref, onMounted } from "vue";
export default {
  name: "Contact",
  components: { BaseButton },
  setup() {
    let form = ref({
      name: null,
      email: null,
      message: null,
    });

    function sendForm() {
      let contactInfo = {
        name: form.value.name.value,
        email: form.value.email.value,
        message: form.value.message.value,
      };
      console.log(contactInfo);
    }

    onMounted(() => {
      let contacts = document.querySelectorAll(".contact_info");
      setTimeout(() => {
        contacts.forEach((info) => {
          info.style.opacity = "1";
          info.style.transform = "scale(1)";
        });
      }, 0);
    });
    return { form, sendForm };
  },
  // data() {
  //   return {
  //     form: {
  //       name: null,
  //       email: null,
  //       message: null,
  //     },
  //   };
  // },
  // methods: {
  //   sendForm() {
  //     let contactInfo = {
  //       name: this.form.name,
  //       email: this.form.email,
  //       message: this.form.message,
  //     };
  //     console.log(contactInfo);
  //     if (window.confirm("Your message is sended.")) {
  //       window.open("Home", "Thanks for visiting!");
  //     }
  //   },
  // },
  // mounted() {
  //   let contacts = document.querySelectorAll(".contact_info");
  //   setTimeout(() => {
  //     contacts.forEach((info) => {
  //       info.style.opacity = "1";
  //       info.style.transform = "scale(1)";
  //     });
  //   }, 0);
  // },
};
</script>

<style scoped>
* {
  transition: all ease-in 0.3s;
}
.contact_page {
  width: 40%;
  margin-top: 10vh;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  /* overflow: hidden; */
}
#title {
  width: 100%;
  margin: 1.25rem;
  text-align: center;
}
form {
  width: 80%;
  padding: 1rem;
}
input {
  padding: 10px 0;
  margin-bottom: 30px;
}
textarea {
  resize: none;
  height: 5rem;
  padding: 10px 0;
  margin-bottom: 40px;
  font-family: "Roboto", sans-serif;
}

textarea,
input[type="text"],
input[type="email"] {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  border-radius: 0;
}
input,
textarea {
  width: 100%;
  outline: none;
  box-sizing: border-box;
  box-shadow: none;
  border: none;
  border-bottom: 2px solid grey;
}

.input_box textarea {
  margin-bottom: 20px;
}
.input_box {
  position: relative;
}

label {
  position: absolute;
  top: 10px;
  left: 0;
  pointer-events: none;
  color: #999;
  font-size: 0.85rem;
}

input:focus ~ label,
input:valid ~ label,
textarea:focus ~ label,
textarea:valid ~ label {
  top: -12px;
  left: 0;
  font-size: 0.75rem;
  font-weight: 600;
  color: #3994ad;
}

input:focus,
input:valid,
textarea:focus,
textarea:valid {
  border-bottom: 2px solid #3994ad;
}

.contact_info {
  opacity: 0;
  transform: scale(0.9);
}
.info_text {
  margin-top: 1rem;
  font-weight: 500;
}

.button {
  display: flex;
  justify-content: center;
  align-items: center;
}
@media (max-width: 600px) {
  .contact_page {
    width: 90%;
  }
}
</style>
