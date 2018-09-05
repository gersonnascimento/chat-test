<template>
  <div id="app">
    <h1>{{ title }} <span class="subtitle">{{ subtitle }}</span></h1>
    <div class="msg_panel">
      <ul class="msg-list">
        <li class="msg" v-for="message of live_messages">
          <p> {{ message }} </p><br>
        </li>
      </ul>
    </div>
    <input v-model="new_message" type="text" @keydown.enter="send_message" placeholder="Digite">
  </div>

</template>

<script>
export default {

  data () {
    return {
      title: 'Teste chat',
      subtitle: 'A vida é boa demais!',
      messages: [
        'Olá!',
        'Tudo bem?'
      ],
      new_message: ''
    }
  },

  computed: {
    live_messages(){
      return this.messages;
    }
  },

  methods: {
    send_message: function(){
      this.messages.push(this.new_message)
      this.new_message = '';
    }
  }


}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
  .subtitle{
    font-size: 15px;
  }
}

ul {
  list-style-type: none;
  padding: 0;
}

a {
  color: #42b983;
}
</style>
