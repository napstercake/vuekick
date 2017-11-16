<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <input type="text" v-model="title" placeholder="add a title"><br /><br />
    <h3 v-if="showTitle">{{ title }}</h3>
    <i v-else>-No title-</i>
    <ul>
      <li v-for="(essential, key) in essentials">
        <a href="#">{{ essential.title }}</a>
      </li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <button v-on:click="greet('Ricardo!')">Say Greeting</button><br><br>
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <hr>
    <label for="">First Name</label> <input type="text" v-model="user.firstName">
    <label for="">Last Name</label> <input type="text" v-model="user.lastName">
    <br><br>
    <h3>{{fullName}}</h3>
    <hr>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      title: 'Hi all!',
      user: {
        firstName: 'Ricardo',
        lastName: 'Gonzales'
      },
      essentials: [
          {title: 'Core Docs', link: 'https://vuejs.org'},
          {title: 'Forum', link: 'https://forum.vuejs.org'},
          {title: 'Community Chat', link: 'https://chat.vuejs.org'},
          {title: 'Twitter', link: 'https://twitter.com/vuejs'}
      ],
      showTitle: true
    }
  },
  methods: {
    greet: function(greeting) {
      alert('say hello! ' + greeting)
    },
    pressKey: function(e) {
      console.log(e.target.value);
    },
    enterHit: function() {
      console.log('you hit enter')
    }
  },
  computed: {
    fullName: function() {
      return this.user.firstName + ' ' + this.user.lastName
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
