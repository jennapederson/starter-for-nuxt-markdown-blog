<template>
  <div class="container">
    <h1 class="title">
      Contact
    </h1>

    <article v-for="msg in messages"
      :key="msg.text"
      class="message"
      :class="msg.type === 'success' ? 'is-success' : 'is-danger'">
      <div class="message-body">
        {{ msg.text }}
      </div>
    </article>

    <section class="contact-form">
      <div class="field">
        <label class="label">Name</label>
        <div class="control">
          <input v-model="contactName" class="input" type="text">
        </div>
      </div>

      <div class="field">
        <label class="label">Email</label>
        <div class="control">
          <input v-model="contactEmail" class="input" type="email">
        </div>
      </div>

      <div class="field">
        <label class="label">Your Message</label>
        <div class="control">
          <textarea v-model="contactMessage" class="textarea" />
        </div>
      </div>

      <div class="field is-grouped">
        <div class="control">
          <button class="button is-link" @click="sendMessage">
            Send Message
          </button>
        </div>
        <div class="control">
          <button class="button is-text" @click="cancelMessage">
            Cancel
          </button>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      messages: [],
      contactName: '',
      contactEmail: '',
      contactMessage: ''
    }
  },
  methods: {
    sendMessage () {
      this.messages = []
      this.triggerSendMessageFunction()
    },
    cancelMessage () {
      this.resetForm()
    },
    resetForm () {
      this.messages = []
      this.contactName = ''
      this.contactEmail = ''
      this.contactMessage = ''
    },
    async triggerSendMessageFunction () {
      try {
        const response = await this.$axios.$post('/.netlify/functions/send-contact-email', {
          contactName: this.contactName,
          contactEmail: this.contactEmail,
          message: this.contactMessage
        })
        this.resetForm()
        this.messages.push({ type: 'success', text: response })
      } catch (error) {
        this.messages.push({ type: 'error', text: error.response.data })
      }
    }
  }
}

</script>
