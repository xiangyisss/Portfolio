<template>
  <div class="contact">
    <h1 class="title"></h1>
    <form action="" class="contact-form" @submit.prevent="submit">
      <label for="name"> <input type="text" placeholder="First Name" /></label>
      <label for="company-name"
        ><input type="text" placeholder="Company Name"
      /></label>
      <label for="email"><input type="email" placeholder="Email" /></label>

      <label for="message">
        <textarea placeholder="Message" />
      </label>
      <input type="submit" class="submit" value="Send Messages" />
    </form>
    <div class="myaddress">
      What's App: + 31 06 123 456 <br />
      E-mail: monster@gmail.com
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
  // data() {
  //   return {
  //     name: "hello",
  //     companyName: "",
  //     email: "",
  //     phoneNumber: "",
  //     message: "",
  //   };
  // },
  // methods: {
  //   submit() {
  //     location.reload();
  //   },
  // },
  methods: {
    submit() {
      location.reload();
      alert("Your message has been recieved.");
    },
  },
};
</script>

<style scoped>
.contact {
  background-color: #fff;
}
.title {
  margin-top: 2rem;
  margin-bottom: 1.5rem;
}
.contact-form {
  display: flex;
  flex-direction: column;
  border: 1px solid snow;
  border-radius: 5px;
  width: 60%;
  margin: auto;
}

.contact-form > * {
  margin-bottom: 0.75rem;
}

.contact-form input,
.contact-form textarea {
  border: 0;
  outline: 0;
  background: transparent;
  border-bottom: 1px solid grey;
  padding-bottom: 0.5rem;
}

.submit {
  width: 40%;
  height: 2rem;
  margin: auto;
  border: 0;
  outline: 0;
  border-radius: 3px;
}
</style>
