<template>
  <div class="message-box">
    <message v-for="message in messages" v-bind:message="message">
  </div>
</template>

<script>
import Message from './Message'

export default {
  name: 'messagebox',
  data () {
    return {
      messages: {}
    }
  },
  methods: {
    loadMessages: function() {
      this.$http.get('https://jsonplaceholder.typicode.com/posts')
        .then(messages => {
          this.messages = messages.body;
        });
    }
  },
  created: function() {
    this.loadMessages();
  },
  components: {
    Message
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
