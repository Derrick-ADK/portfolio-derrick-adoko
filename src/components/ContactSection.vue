
<script setup>
import { ref } from 'vue'
import { Mail, Linkedin, Github, Send } from 'lucide-vue-next'

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const loading = ref(false)
const feedback = ref('')
const success = ref(false)

const submitForm = async () => {
  loading.value = true
  feedback.value = ''
  success.value = false

  try {
    const response = await fetch(
      'https://formspree.io/f/xljblwdl',
      {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          Accept: 'application/json'
        },
        body: JSON.stringify(form.value)
      }
    )

    if (!response.ok) {
      throw new Error('Erreur lors de l’envoi.')
    }

    success.value = true
    feedback.value = 'Votre message a bien été envoyé.'

    form.value = {
      name: '',
      email: '',
      subject: '',
      message: ''
    }

  } catch (error) {
    feedback.value =
      'Impossible d’envoyer le message. Réessayez plus tard.'
  } finally {
    loading.value = false
  }
}
</script>

<template>
  <section id="contact" class="section">

    <div class="section-container">

      <div class="contact-box">

        <span class="section-label">05 — CONTACT</span>

        <h2>
          Construisons quelque chose
          <span>d'intéressant ensemble.</span>
        </h2>

        <p>
          Une opportunité professionnelle, un projet ou une
          collaboration ? Je serais ravi d'échanger avec vous.
        </p>

        <form
          class="contact-form"
          @submit.prevent="submitForm"
        >

          <div class="form-row">

            <label>
              Nom complet
              <input
                v-model="form.name"
                type="text"
                placeholder="Votre nom"
                autocomplete="name"
                required
              />
            </label>

            <label>
              Adresse e-mail
              <input
                v-model="form.email"
                type="email"
                placeholder="vous@exemple.com"
                autocomplete="email"
                required
              />
            </label>

          </div>

          <label>
            Objet
            <input
              v-model="form.subject"
              type="text"
              placeholder="Objet de votre message"
              required
            />
          </label>

          <label>
            Votre message
            <textarea
              v-model="form.message"
              rows="6"
              placeholder="Écrivez votre message ici..."
              required
            ></textarea>
          </label>

          <button
            type="submit"
            class="btn-primary"
            :disabled="loading"
          >
            {{ loading ? 'Envoi en cours...' : 'Envoyer le message' }}
            <Send :size="18" />
          </button>

          <p
            v-if="feedback"
            class="form-feedback"
            :class="{ success: success }"
            role="status"
            aria-live="polite"
          >
            {{ feedback }}
          </p>

        </form>

        <div class="contact-links">

          <a href="mailto:adokoayide@gmail.com">
            <Mail />
            adokoayide@gmail.com
          </a>

          <a
            href="https://www.linkedin.com/in/derrick-adoko/"
            target="_blank"
            rel="noopener noreferrer"
          >
            <Linkedin />
            Derrick ADOKO
          </a>

          <a
            href="https://github.com/Derrick-ADK"
            target="_blank"
            rel="noopener noreferrer"
          >
            <Github />
            Derrick ADK
          </a>

        </div>

      </div>

    </div>

  </section>
</template>
