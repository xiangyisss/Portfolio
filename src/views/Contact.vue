<template>
  <div class="contact-page">
    <div id="title">
      <h1 class="contact-info">Get in touch</h1>
      <p class="contact-info info-text">
        Feel free to contact me, I will get back to you as soon as possible.
      </p>
    </div>
    <form action="" class="contact-info" autocomplete="off">
      <!-- <div class="name-section">
        <input type="text" v-model="form.name" required />
        <label for="name" class="label-name">
          <span class="content-name">Name</span>
        </label>
      </div>

      <div class="email-section">
        <input type="text" v-model="form.email" required />
        <label for="email" class="label-name">
          <span class="content-name">E-mail</span>
        </label>
      </div>

      <div class="message-section">
        <textarea type="text" v-model="form.message" required />
        <label for="message" class="message-name">
          <span class="content-name">Your message</span>
        </label>
      </div> -->

      <label for="name" class="label-name">
        <input type="text" name="Name" v-model="form.name" required />
        <span class="content-name">Name</span>
      </label>

      <label for="email">
        <input type="email" v-model="form.email" required />
        <span class="content-name">Email</span>
      </label>

      <label for="message">
        <textarea v-model="form.message" required />
        <span class="content-name">Message</span>
      </label>
      <div class="button">
        <button type="submit" class="submit-button" @submit.prevent="sendForm">
          Submit
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Contact",
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
  // mounted() {
  //   let contact = document.querySelectorAll(".contact-info");
  //   let delay = 0;
  //   setTimeout(() => {
  //     contact.forEach((info) => {
  //       delay += 0.1;
  //       info.style.opacity = "1";
  //       info.style.transform = "translateY(40px)";
  //       info.style.transform = "translateX(-60px)";
  //       info.style.transitionDelay = delay + "s";
  //     });
  //   });
  // },
  mounted() {
    let contacts = document.querySelectorAll(".contact-info");
    // let delay = 0.1;

    setTimeout(() => {
      contacts.forEach((info) => {
        // delay += 0.1;
        info.style.opacity = "1";
        info.style.transform = "scale(1)";
        // info.style.transitionDelay = delay + "s";
      });
    });
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
  /* box-shadow: 4px 8px 16px 1px rgba(179, 179, 179, 0.2); */
  border-right: 1px solid rgba(255, 255, 255, 0.089);
  border-bottom: 1px solid rgba(255, 255, 255, 0.089);
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
  height: 48px;
  padding: 0px 0 0 8px;
  outline: none;
  border: 1px solid rgb(116, 116, 116);
  border-radius: 4px;
  margin-bottom: 1.25rem;
}

textarea {
  resize: none;
  padding: 20px 0 0 8px;
  height: 80px !important;
  font-family: "Roboto", sans-serif;
}

input:focus + .content-name,
textarea:focus + .content-name {
  background-color: white;
  color: #3994ad;
  border-radius: 2px;
  top: -7px;
  padding: 0.25rem;
}

input:focus,
textarea:focus {
  border: 1px solid #3994ad;
}

.button {
  display: flex;
  justify-content: center;
  align-items: center;
}
/* 
.submit-button {
  width: 40%;
  padding: 0.5rem;
  margin-top: 1.5rem;
  background-color: transparent;
  border: 1px solid #44cfcb;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 500;
  font-family: "Roboto", sans-serif;
} */

.mysms {
  width: 80%;
}
.sms {
  display: flex;
  justify-content: start;
  align-items: center;
  width: 80%;
  margin: 0 auto;
}

.sms img {
  display: block;
  /* width: 20px; */
  height: 20px;
  margin: 1rem 1rem 1rem 1rem;
  filter: invert(17%) sepia(94%) saturate(7381%) hue-rotate(296deg)
    brightness(83%) contrast(108%);
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
  padding-left: 4px;
  position: absolute;
  top: 16px;
  left: 8px;
}

.submit-button {
  width: 110px;
  height: 44px;
  text-align: center;
  font-size: 1rem;
  font-weight: 600;
  border: 2px solid #44a7c3;
  background-color: transparent;
  color: #44a7c3;
  border-radius: 4px;
  line-height: 44px;
  cursor: pointer;
  position: relative;
  overflow: hidden;
}

.submit-button::before {
  content: " ";
  width: 110px;
  height: 44px;
  background-color: #44a8c344;
  border: none;
  position: absolute;
  z-index: -1;
  left: 0;
  top: -2px;
  border-radius: 4px;
  transform: translateX(-110px);
}

.submit-button:hover::before {
  transform: translateX(0%);
  transition: all 0.2s ease;
}
</style>
