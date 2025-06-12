<script setup>
  import { ref } from 'vue';
  import emailjs from 'emailjs-com';

  // Definir los datos del formulario
  const formData = ref({
    user_name: '',
    user_email: '',
    company: '',
    message: ''
  });

  // Variables de estado para manejar el proceso de envío
  const loading = ref(false);
  const buttonText = ref('Enviar mensaje');

  // Configuración para enviar el correo a través de EmailJS
  const sendEmail = () => {
    loading.value = true;
    buttonText.value = 'Enviando...';

    const serviceID = 'service_x2ytbra'; // Tu Service ID de EmailJS
    const templateID = 'template_dnwz9nl'; // Tu Template ID de EmailJS
    const userID = 'aBP3-dztxEzdthbRq'; // Tu User ID de EmailJS

    // Iniciar EmailJS con tu User ID
    emailjs.init(userID);

    // Enviar el correo utilizando send con los datos del formulario
    const emailParams = {
      user_name: formData.value.user_name,
      user_email: formData.value.user_email,
      company: formData.value.company,
      message: formData.value.message
    };

    emailjs.send(serviceID, templateID, emailParams)
      .then(() => {
        loading.value = false;
        buttonText.value = 'Mensaje enviado';
        // Resetear formulario después de enviarlo
        formData.value = {
          user_name: '',
          user_email: '',
          company: '',
          message: ''
        };
      }, (err) => {
        loading.value = false;
        buttonText.value = 'Enviar mensaje';
        alert('Error al enviar el correo: ' + JSON.stringify(err));
      });
  };
</script>

<template>
  <div class="contact-form card">
    <form @submit.prevent="sendEmail" id="form">
      <div class="form-group">
        <label for="user_name">Nombre</label>
        <input type="text" id="user_name" v-model="formData.user_name" required />
      </div>

      <div class="form-group">
        <label for="user_email">Correo electrónico</label>
        <input type="email" id="user_email" v-model="formData.user_email" required />
      </div>

      <div class="form-group">
        <label for="company">Empresa</label>
        <input type="text" id="company" v-model="formData.company" />
      </div>

      <div class="form-group">
        <label for="msg">Mensaje</label>
        <textarea id="msg" v-model="formData.message" required></textarea>
      </div>

      <button type="submit" :disabled="loading">{{ buttonText }}</button>
    </form>
  </div>
</template>


<style scoped>
.contact-form {
  width: 90%;
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  display: flex;
  flex-direction: column;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.form-group {
  width: 100%;
  margin-bottom: 10px;
}

.form-group label {
  font-weight: 500;
  margin-bottom: 5px;
  display: block;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  background-color: transparent;
  border: 2px solid var(--color-primary);
  font-size: 1rem;
  outline: none;
}

.form-group textarea {
  min-height: 200px;
  resize: vertical;
}

button {
  padding: 10px 20px;
  background-color: var(--color-primary);
  color: white;
  border: none;
  border-radius: 10px;
  font-size: 1rem;
  cursor: pointer;
  width: 100%;
}

button:disabled {
  background-color: #ccc;
  cursor: not-allowed;
}
</style>

  
  