<template>
  <div class="contact">
    <form ref="form" @submit.prevent="sendEmail">
      <label class="text">Nom/Prénom</label>
      <input type="text" name="user_name">
      <label class="text">Email</label>
      <input type="email" name="user_email">
      <label class="text">Message</label>
      <textarea name="message"></textarea>
      <input type="submit" value="Envoyer">
    </form>
  </div>

</template>

<script>
import emailjs from '@emailjs/browser';

export default {
  methods: {
    sendEmail() {
      emailjs.sendForm('service_8so1riz', 'template_tbxu796', this.$refs.form, 'FUrKh9zPwp0uosEcY')
          .then((result) => {
            console.log('SUCCESS!', result.text);
          }, (error) => {
            console.log('FAILED...', error.text);
          });
    }
  }
}
</script>

<style scoped lang="scss">
@import "src/scss/foundations/variable.scss";


text {
  font-family: $portfolioMainTitle_font;
}

form {
  display: flex;
  flex-direction: column;
  margin-bottom: $-sp-m;
  margin-top: $-sp-m;
  max-width: 1000px;
}

input[type=submit] {
  position: center;
  width: 150px;
  margin-left: 400px;
  margin-right: 500px;
  margin-top: 20px;
  cursor:pointer;
  border-radius: 10px;
  font-family: $portfolioMainTitle_font;
  font-size: $-t-s;
  color: $portfolioBackground;
  border: 2px solid $portfolioBackground;
  background-color: rgba(255,255,255,1);
  transition: all ease-in .3s;
  &:hover {
    background-color: rgba(255,255,255,0);
    border-color: white;
    color: white;
  }
}





</style>