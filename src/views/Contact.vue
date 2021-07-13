<template>
  <div class="contact">
    <div id="title">
      <h1 class="title contact-info">Contact</h1>
    </div>
    <form action="" id="contact-form" class="contact-info" autocomplete="off">
      <div class="name-section">
        <input type="text" v-model="form.name" required />
        <label for="name" class="label-name">
          <span class="content-name">Name</span>
        </label>
      </div>

      <!-- <label for="name" class="label-name">
        <input type="text" name="Name" v-model="form.name" />
        <span>Name</span>
      </label> -->
      <!-- 
      <label for="email">
        <span>Email</span>
        <input type="email" v-model="form.email" />
      </label>

      <label for="subject">
        <span>Subject</span>
        <input type="text" v-model="form.subject" />
      </label>

      <label for="message">
        <span>Your message</span>
        <textarea v-model="form.message" />
      </label>
      <button type="submit" class="submit-button" @submit.prevent="sendForm">
        Submit your form
      </button> -->
    </form>

    <!-- <div class="mysms contact-info">
      <div class="sms">
        <img src="../assets/whatsapp.svg" class="whatsapp-img" />
        + 31 06 123 456
      </div>
      <div class="sms">
        <img src="../assets/linkedIn.svg" class="linkedin-img" />
        Follow me on Linkedin
      </div>
    </div> -->
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
        subject: null,
        message: null,
      },
    };
  },
  methods: {
    sendForm() {
      let contactInfo = {
        name: this.form.name,
        email: this.form.email,
        subject: this.form.subject,
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
.name-section {
  width: 100%;
  height: 50px;
  position: relative;
  overflow: hidden;
}

form input {
  width: 100%;
  height: 100%;
  padding-top: 20px;
  border: none;
  outline: none;
}

form label {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  border-bottom: 1px solid rgb(63, 62, 62);
}

form label::after {
  content: "";
  position: absolute;
  width: 100%;
  height: 100%;
  border-bottom: 3px solid #44a7c3;
  left: 0;
  bottom: -1px;
  transform: translateX(-100%);
  transition: transform 0.3s ease-in;
}

.content-name {
  position: absolute;
  bottom: 5px;
  left: 0;
}

form input:focus + .label-name .content-name,
form input:valid + .label-name .content-name {
  transform: translateY(-150%);
  font-size: 0.75rem;
  color: #44a7c3;
}

form input:focus + .label-name::after,
form input:valid + .label-name::after {
  transform: translateX(0%);
}

* {
  transition: all ease-in 0.3s;
}
.contact {
  background-color: white;
  width: 40%;
  padding: 1rem;
  /* height: 80%; */
  /* display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: space-around; */
  /* opacity: 0;
  transform: scale(0.5); */
}

#title {
  width: 100%;
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
  width: 100%;
  padding: 1rem;
  position: relative;
}
/*
#contact-form input,
#contact-form textarea {
  transition: all ease-in 0.3s;
  display: block;
  width: 100%;
  height: 100%;
  margin: 0 auto 1.5rem auto;

  outline: none;
  border: none;

  border-bottom: 1px solid rgb(190, 182, 219);
  font-size: 0.875rem;
  font-family: "Roboto", sans-serif;
} */

/* #contact-form input:focus,
#contact-form textarea:focus {
  border-bottom: 1px solid gray;
} */

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
  font-family: "Roboto", sans-serif;
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
  transform: scale(0.3);
}
</style>
