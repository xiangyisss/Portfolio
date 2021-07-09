<template>
  <div class="contact">
    <div id="title">
      <h1 class="title contact-info">Contact</h1>
    </div>
    <form action="" id="contact-form" autocomplete="off" class="contact-info">
      <label for="name">
        <input type="text" placeholder="Name" v-model="form.name" />
      </label>

      <!-- <label for="name" class="label-name">
        <input type="text" name="Name" v-model="form.name" />
        <span>Name</span>
      </label> -->

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

    <div class="mysms contact-info">
      <div class="sms">
        <img src="../assets/whatsapp.svg" class="whatsapp-img" />
        + 31 06 123 456
      </div>
      <div class="sms">
        <img src="../assets/linkedIn.svg" class="linkedin-img" />
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
  mounted() {
    let contact = document.querySelectorAll(".contact-info");
    let delay = 0;
    setTimeout(() => {
      contact.forEach((info) => {
        delay += 0.1;
        info.style.opacity = "1";
        info.style.transform = "translateY(40px)";
        info.style.transform = "translateX(-60px)";
        info.style.transitionDelay = delay + "s";
      });
    });
  },
};
</script>

<style scoped>
* {
  transition: all ease-in 0.3s;
}
.contact {
  /* background-color: gold; */
  width: 50%;
  height: 80%;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around;
}

#title {
  width: 80%;
}
.title {
  text-align: center;
  margin-top: 1.25rem;
  margin-bottom: 1.25rem;
  /* background-color: salmon; */
}
#contact-form {
  display: flex;
  flex-direction: column;
  width: 80%;
  padding: 1rem;
}

#contact-form input,
#contact-form textarea {
  transition: all ease-in 0.3s;
  display: block;
  width: 80%;
  margin: 0 auto 1.5rem auto;
  padding-bottom: 0.5rem;
  padding-left: 0.25rem;
  outline: none;
  border: none;
  border-bottom: 1px solid plum;
  font-size: 0.875rem;
  font-family: "Roboto", sans-serif;
}

#contact-form input:focus,
#contact-form textarea:focus {
  border-bottom: 1px solid gray;
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
  transform: translateY(-40px);
}
</style>
