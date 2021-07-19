<template>
  <div class="contact-page">
    <div id="title">
      <h1 class="contact-info">Get in touch</h1>
      <p class="contact-info info-text">
        Feel free to contact me, I will get back to you as soon as possible.
      </p>
    </div>
    <form action="" class="contact-info" autocomplete="off">
      <label for="name">
        <input type="text" name="name" v-model="form.name" required />
        <span class="content-name">Name</span>
      </label>

      <label for="email">
        <input type="email" name="email" v-model="form.email" required />
        <span class="content-name">Email</span>
      </label>

      <label for="message">
        <textarea v-model="form.message" name="message" required />
        <span class="content-name">Message</span>
      </label>
      <!-- <div class="button">
        <button type="submit" class="submit-button" @submit.prevent="sendForm">
          Submit
        </button>
      </div> -->
      <BaseButton type="submit" @submit.prevent="sendForm"></BaseButton>
    </form>
  </div>
</template>

<script>
import BaseButton from "@/components/BaseButton.vue";
export default {
  name: "Contact",
  components: { BaseButton },
  data() {
    return {
      form: {
        name: null,
        email: null,
        message: null,
      },
    };
  },
  methods: {
    sendForm() {
      let contactInfo = {
        name: this.form.name,
        email: this.form.email,
        message: this.form.message,
      };
      console.log(contactInfo);
    },
  },
  mounted() {
    let contacts = document.querySelectorAll(".contact-info");
    setTimeout(() => {
      contacts.forEach((info) => {
        info.style.opacity = "1";
        info.style.transform = "scale(1)";
      });
    }, 0);
  },
};
</script>

<style scoped>
* {
  transition: all ease-in 0.3s;
}
.contact-page {
  width: 40%;
  margin-top: 10vh;
  padding: 1rem;
  /* border-right: 1px solid rgba(255, 255, 255, 0.089);
  border-bottom: 1px solid rgba(255, 255, 255, 0.089); */
  display: flex;
  flex-direction: column;
  align-items: center;
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

label {
  position: relative;
}
input,
textarea {
  display: block;
  width: 100%;
  height: 3rem;
  padding: 0px 0 0 8px;
  outline: none;
  border: 1px solid rgb(116, 116, 116);
  border-radius: 4px;
  margin-bottom: 1.25rem;
}

textarea {
  resize: none;
  padding: 1.25rem 0 0 0.5rem;
  height: 5rem !important;
  font-family: "Roboto", sans-serif;
}

input:focus + .content-name,
textarea:focus + .content-name,
input:valid + .content-name,
textarea:valid + .content-name {
  background-color: white;
  color: #3994ad;
  border-radius: 2px;
  top: -8px;
  padding: 4px;
}

input:focus,
textarea:focus {
  border: 1px solid #3994ad;
}

.contact-info {
  opacity: 0;
  transform: scale(0.9);
}

.info-text {
  margin-top: 1rem;
  font-weight: 500;
}

span {
  color: rgb(99, 95, 95);
  font-size: 0.75rem;
  padding-left: 0.25rem;
  position: absolute;
  top: 1.125rem;
  left: 0.5rem;
  pointer-events: none;
}

.button {
  display: flex;
  justify-content: center;
  align-items: center;
}

.submit-button {
  width: 6.875rem;
  height: 2.75rem;
  text-align: center;
  font-size: 1rem;
  font-weight: 600;
  border: 2px solid #44a7c3;
  background-color: transparent;
  color: #44a7c3;
  border-radius: 4px;
  line-height: 2.75rem;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.submit-button::before {
  content: " ";
  width: 6.875rem;
  height: 2.75rem;
  background-color: #44a8c344;
  border: none;
  position: absolute;
  z-index: -1;
  left: 0;
  top: -0.125rem;
  border-radius: 4px;
  transform: translateX(-6.875rem);
}

.submit-button:hover::before {
  transform: translateX(0%);
  transition: all 0.2s ease;
}

@media (max-width: 414px) {
  .contact-page {
    width: 90%;
  }
}
</style>
