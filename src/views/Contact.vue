<template>
  <div class="contact-page">
    <div id="title">
      <h1 class="contact-info">Contact</h1>
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
  /* background-color: white; */
  width: 40%;
  padding: 1rem;
  box-shadow: 4px 8px 16px 1px rgba(179, 179, 179, 0.2);
  display: flex;
  flex-direction: column;
  align-items: center;
}

#title {
  width: 100%;
  margin: 1.25rem 0 1.25rem 0;
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
  color: #344a5f;
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
.submit-button {
  width: 40%;
  padding: 0.5rem;
  margin-top: 1.5rem;
  background-color: transparent;
  border: 1px solid #619aaa;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 500;
  font-family: "Roboto", sans-serif;
}

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
  transform: scale(0.3);
}

span {
  color: silver;
  font-size: 0.75rem;
  padding-left: 4px;
  position: absolute;
  top: 16px;
  left: 8px;
}
</style>
