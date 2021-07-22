<template>
  <div class="contact_page">
    <div id="title">
      <h1 class="contact_info">Get in touch</h1>
      <p class="contact_info info_text">
        Feel free to contact me, I will get back to you as soon as possible.
      </p>
    </div>
    <form action="" class="contact_info" autocomplete="off">
      <div class="section">
        <input type="text" name="name" v-model="form.name" required />
        <label for="name" class="label_name">
          <span class="content_name">Name</span>
        </label>
      </div>

      <div class="section">
        <input type="email" name="email" v-model="form.email" required />
        <label for="email" class="label_name">
          <span class="content_name">Email</span>
        </label>
      </div>

      <div class="section">
        <input type="text" name="message" v-model="form.message" required />
        <label for="message" class="label_name">
          <span class="content_name">Message</span>
        </label>
      </div>

      <!-- <label for="email">
        <input type="email" name="email" v-model="form.email" required />
        <span class="content_name">Email</span>
      </label> -->

      <!-- <label for="message">
        <textarea v-model="form.message" name="message" required />
        <span class="content_name">Message</span>
      </label> -->

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
    let contacts = document.querySelectorAll(".contact_info");
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
/* * {
  transition: all ease-in 0.3s;
} */
.contact_page {
  width: 40%;
  margin-top: 10vh;
  padding: 1rem;

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

.section {
  width: 100%;
  height: 2.5rem;
  position: relative;
  margin-bottom: 2rem;
}

input {
  width: 100%;
  height: 100%;
  padding-top: 20px;
  border: none;
  outline: none;
}

label {
  position: absolute;
  width: 100%;
  height: 100%;
  left: 0;
  bottom: 0;
  pointer-events: none;
  border-bottom: 1px solid rgb(46, 46, 46);
  color: grey;
  font-size: 0.85rem;
}
label::after {
  content: "";
  width: 5%;
  height: 100%;
  position: absolute;
  right: 0;
  bottom: -1px;
  border-bottom: 2px solid #44a7c3;
  opacity: 0;
}

input:focus + .label_name::after,
input:valid + .label_name::after {
  width: 100%;
  opacity: 1;
  transition: width 0.2s ease-in;
}
.content_name {
  position: absolute;
  bottom: 5px;
  left: 0;
}

input:focus + .label_name .content_name,
input:valid + .label_name .content_name {
  transform: translateY(-150%);
  font-size: 0.75rem;
  font-weight: 600;
  color: #44a7c3;
  transition: all 0.2s ease-in;
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
