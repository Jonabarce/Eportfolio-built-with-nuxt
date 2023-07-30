<template>
  <div class="contact-wrapper">
    <div class="contact-container">
      <div class="contact-info-div">
        <h1>Contact me</h1>
        <p id="middle-sentence">
          Do you want to know more about me? <br />Get in touch via this form or
          via email <br />
          <a target="_blank" href="mailto:javevang1@gmail.com">
            <Icon class="the-icon" name="fluent-emoji:e-mail" />
          </a>
        </p>
      </div>

      <div class="contact-form-div">
        <form @submit.prevent="checkInputFields">
          <h2>Send me a message!</h2>
          <span class="colon-1">
            <span class="colon-1-inp">
              <label for="firstName">First name:</label>
              <input
                type="text"
                id="firstName"
                v-model="firstName"
                @input="validateFirstName"
                :class="{ 'input-error': firstNameError }"
              />
              <p class="error-message" v-if="firstNameError">
                {{ firstNameError }}
              </p>
            </span>

            <span class="colon-1-inp">
              <label for="lastName">Surname:</label>
              <input
                type="text"
                id="lastName"
                v-model="lastName"
                @input="validateLastName"
                :class="{ 'input-error': lastNameError }"
              />
              <p class="error-message" v-if="lastNameError">
                {{ lastNameError }}
              </p>
            </span>
          </span>

          <span class="colon-2">
            <span class="colon-2-inp">
              <label for="email">E-mail:</label>
              <input
                type="email"
                id="email"
                v-model="email"
                @input="validateEmail"
                :class="{ 'input-error': emailError }"
              />
              <p class="error-message" v-if="emailError">{{ emailError }}</p>
            </span>
          </span>

          <span class="colon-3">
            <span class="colon-3-inp">
              <label for="message">Message:</label>
              <textarea
                class="message-area"
                id="message"
                v-model="message"
                @input="validateMessage"
              ></textarea>
              <p class="error-message" v-if="messageError">
                {{ messageError }}
              </p>
            </span>
          </span>

          <span class="colon-4">
            <input type="submit" value="Send a message" />
            <p>{{ feedbackMessage }}</p>
          </span>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

import emailjs from 'emailjs-com'

const emailjsApiKey = ref('')
const emailjsServiceID = ref('')
const emailjsTemplateID = ref('')

onMounted(() => {
  emailjsApiKey.value = import.meta.env.VITE_EMAILJS_API_KEY.trim()
  emailjsServiceID.value = import.meta.env.VITE_EMAILJS_SERVICE_ID.trim()
  emailjsTemplateID.value = import.meta.env.VITE_EMAILJS_TEMPLATE_ID.trim()
  emailjs.init(emailjsApiKey.value)
})

const firstName = ref('')
const lastName = ref('')
const email = ref('')
const message = ref('')
const feedbackMessage = ref('')
const firstNameError = ref('')
const lastNameError = ref('')
const emailError = ref('')
const messageError = ref('')

const validateFirstName = () => {
  if (isFieldEmpty(firstName.value)) {
    firstNameError.value = 'First name is required.'
  } else {
    firstNameError.value = ''
  }
}

const validateLastName = () => {
  if (isFieldEmpty(lastName.value)) {
    lastNameError.value = 'Surname is required.'
  } else {
    lastNameError.value = ''
  }
}

const validateEmail = () => {
  if (isFieldEmpty(email.value) || !isEmailValid(email.value)) {
    emailError.value = 'A valid email address is required.'
  } else {
    emailError.value = ''
  }
}

const validateMessage = () => {
  if (isFieldEmpty(message.value)) {
    messageError.value = 'Message is required.'
  } else {
    messageError.value = ''
  }
}

const isEmailValid = (email) => {
  const regex = /^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/
  return regex.test(email)
}

const isFieldEmpty = (field) => {
  return field.trim() === ''
}

const checkInputFields = () => {
  validateFirstName()
  validateLastName()
  validateEmail()
  validateMessage()

  const hasErrors =
    firstNameError.value ||
    lastNameError.value ||
    emailError.value ||
    messageError.value
  if (!hasErrors) {
    sendEmail()
  }
}

const sendEmail = () => {
  const templateParams = {
    from_name: `${firstName.value} ${lastName.value}`,
    from_email: email.value,
    to_name: 'Her kommer en epost fra nettsiden din',
    message: message.value
  }
  emailjs
    .send(emailjsServiceID.value, emailjsTemplateID.value, templateParams)
    .then(
      () => {
        feedbackMessage.value = 'Your message has been sent!'
        firstName.value = ''
        lastName.value = ''
        email.value = ''
        message.value = ''
      },
      (error) => {
        feedbackMessage.value = 'The message was not sent... Try again!'
      }
    )
}
</script>

<style scoped>
.contact-wrapper {
  padding: 1rem;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
  width: 95%;
}

.the-icon {
  height: 2.7rem;
  width: 2.7rem;
}

.contact-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 7rem;
  padding: 3rem;
  border-radius: 10px;
}

.contact-info-div {
  padding: 2rem;
}

.contact-info-div h1 {
  color: #0369dd;
}

.contact-info-div p {
  color: #525252;
  font-family: Mulish, sans-serif;
}

#middle-sentence {
  font-size: 1.2rem;
}

#ending-sentence {
  font-size: 1.4rem;
}

.contact-form-div h2 {
  padding: 1rem;
  color: #ffffff;
}

.contact-form-div h1 {
  padding: 1rem;
}

.contact-form-div {
  display: flex;
  justify-content: center;
  border-radius: 0.6rem;
  padding: 1rem;
  background-color: #3f3f46;
  border-radius: 1.7rem;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.4);
}

.colon-1,
.colon-2,
.colon-3,
.colon-4 {
  display: flex;
  flex-direction: column;
  margin-bottom: 2rem;
  color: #ffffff;
  font-family: Mulish, sans-serif;
}

.colon-1 {
  flex-direction: row;
  justify-content: space-between;
}

.colon-1-inp,
.colon-2-inp,
.colon-3-inp {
  width: 100%;
}

.colon-1-inp:first-child {
  margin-right: 1rem;
}

input[type='text'],
input[type='email'],
textarea {
  padding: 1rem;
  border-radius: 5px;
  width: 100%;
  box-sizing: border-box;
  font-size: 1rem;
  margin-top: 0.5rem;
  font-family: Poppins, sans-serif;
}

input[type='text']:focus,
input[type='email'],
textarea:focus {
  outline: none;
}

textarea {
  resize: none;
  height: 10rem;
}

input[type='submit'] {
  border: none;
  border-radius: 5px;
  padding: 1rem 2rem;
  cursor: pointer;
  transition: background-color 0.1s ease;
}

@media only screen and (max-width: 1100px) {
  .contact-container {
    display: flex;
    flex-direction: column;
  }
}

@media only screen and (max-width: 680px) {
  .colon-1 {
    flex-direction: column;
  }

  .colon-1-inp:first-child {
    margin-bottom: 0.5rem;
  }

  .contact-container {
    padding: 1rem;
    gap: 1rem;
  }
  .contact-form-div h2 {
    font-size: 1.1rem;
  }
}
</style>
