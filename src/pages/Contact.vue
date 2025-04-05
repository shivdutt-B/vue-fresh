<script setup>
import { ref } from "vue";

const name = ref("");
const email = ref("");
const message = ref("");

function submitForm() {
  // In a real application, you would process the form submission here
  console.log("Form submitted:", {
    name: name.value,
    email: email.value,
    message: message.value,
  });
  alert("Thank you for your message! We will get back to you soon.");
  name.value = "";
  email.value = "";
  message.value = "";
}
</script>

<template>
  <div class="contact-page">
    <div class="contact-header">
      <h1>Contact Us</h1>
      <p>
        We'd love to hear from you! Fill out the form below to get in touch.
      </p>
    </div>

    <div class="contact-container">
      <div class="contact-info">
        <h2>Our Information</h2>
        <div class="info-item">
          <strong>Address:</strong>
          <p>123 Vue Street, Web Dev City</p>
        </div>
        <div class="info-item">
          <strong>Email:</strong>
          <p>contact@example.com</p>
        </div>
        <div class="info-item">
          <strong>Phone:</strong>
          <p>+1 (555) 123-4567</p>
        </div>
      </div>

      <div class="contact-form">
        <h2>Send a Message</h2>
        <form @submit.prevent="submitForm">
          <div class="form-group">
            <label for="name">Name</label>
            <input
              type="text"
              id="name"
              v-model="name"
              placeholder="Your name"
              required
            />
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input
              type="email"
              id="email"
              v-model="email"
              placeholder="Your email"
              required
            />
          </div>
          <div class="form-group">
            <label for="message">Message</label>
            <textarea
              id="message"
              v-model="message"
              placeholder="Your message"
              rows="5"
              required
            ></textarea>
          </div>
          <button type="submit" class="submit-btn">Send Message</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contact-page {
  max-width: 1000px;
  margin: 0 auto;
  padding: 20px;
}

.contact-header {
  text-align: center;
  margin-bottom: 40px;
}

.contact-header h1 {
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 10px;
}

.contact-header p {
  font-size: 1.1rem;
  color: #666;
}

.contact-container {
  display: flex;
  gap: 40px;
}

.contact-info,
.contact-form {
  flex: 1;
}

.contact-info {
  background-color: #f5f5f5;
  padding: 30px;
  border-radius: 8px;
}

.info-item {
  margin-bottom: 20px;
}

.info-item strong {
  display: block;
  margin-bottom: 5px;
  color: #42b883;
}

.contact-form {
  background-color: white;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 8px;
  font-weight: 600;
}

input,
textarea {
  width: 100%;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 1rem;
}

input:focus,
textarea:focus {
  border-color: #42b883;
  outline: none;
}

.submit-btn {
  background-color: #42b883;
  color: white;
  border: none;
  padding: 12px 24px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 600;
  transition: background-color 0.3s;
}

.submit-btn:hover {
  background-color: #3aa876;
}

@media (max-width: 768px) {
  .contact-container {
    flex-direction: column;
  }
}
</style>
