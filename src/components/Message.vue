<template>
  <div class="message">
    <h2>{{message.title}}</h2>
    <h3>By {{user}}</h3>
    <p>{{message.body}}</p>
  </div>
</template>

<script>
export default {
  name: 'message',
  data () {
    return {
      user: ""
    }
  },
  methods: {
    getUser: function() {
      this.$http.get('https://jsonplaceholder.typicode.com/users/' + this.message.userId)
        .then(res => {
          this.user = res.body.username;
        });
    }
  },
  created : function() {
    this.getUser();
  },
  props: ['message']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h2 {
    font-size: 20px;
    margin-bottom: 5px;
  }

  p {
    margin-top: 0;
    font-size: 16px;
  }
</style>
