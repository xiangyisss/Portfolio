<template>
  <div class="contact">
    <h1 class="title">Contact</h1>
    <form action="" id="contact-form">
      <label for="name">
        <input type="text" placeholder="Name" v-model="form.name"
      /></label>

      <label for="email"
        ><input type="email" placeholder="Email" v-model="form.email"
      /></label>

      <label for="message">
        <textarea placeholder="Message" v-model="form.message" />
      </label>
      <button type="submit" class="submit-button" @submit.prevent="sendForm">
        Submit your form
      </button>
    </form>
    <div class="mysms">
      <div class="sms">
        <img src="../assets/whatsapp.svg" class="whatsapp-img" />
        + 31 06 123 456
      </div>
      <div class="sms">
        <img src="../assets/linkedin.svg" class="linkedin-img" />
        Follow me on Linkedin
      </div>
    </div>
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
};
</script>

<style scoped>
.contact {
  /* background-color: gold; */
  width: 50%;
  height: 80%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}

.title {
  margin-top: 1.25rem;
  margin-bottom: 1.25rem;
}
#contact-form {
  display: flex;
  flex-direction: column;
  width: 80%;
}

#contact-form input,
#contact-form textarea {
  width: 100%;
  padding-bottom: 0.5rem;
  padding-left: 0.25rem;
  outline: none;
  border: none;
  border-bottom: 1px solid plum;
  margin-bottom: 1.5rem;
  background: transparent;
  font-size: 0.875rem;
  font-family: "Source Serif Pro", serif;
}

#contact-form textarea {
  resize: none;
  height: 80%;
}

.submit-button {
  width: 60%;
  margin: 1rem auto 0 auto;
  padding: 0.5rem;
  font-size: 1rem;
  font-weight: 600;
  font-family: "Source Serif Pro", serif;
  background-color: transparent;
  border: none;
  border: 1px solid plum;
  border-radius: 4px;
  cursor: pointer;
}

.mysms {
  width: 80%;
}
.sms {
  /* background-color: salmon; */
  display: flex;
  justify-content: start;
  align-items: center;
  width: 100%;
}

.sms img {
  display: block;
  /* width: 20px; */
  height: 20px;
  margin: 1rem 1rem 1rem 1rem;
}
</style>
