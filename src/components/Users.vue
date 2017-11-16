<template>
  <div class="users">
    <h1>Users</h1>
    <p>
        <form v-on:submit="addUser">
            <input type="text" v-model="newUser.name" placeholder="Enter your name">
            <input type="text" v-model="newUser.email" placeholder="Enter your email">
            <input type="submit" value="Submit">
        </form>
    </p>
    <ul>
        <li v-for="user in users">
            <input type="checkbox" class="toogle" v-model="user.contacted">
            {{user.name}}: {{user.email}}
        </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'users',
  data () {
    return {
      newUser: {},
      users: [
        {
          name: 'Ricardo Gonzales',
          email: 'jricardo@gmail.com',
          contacted: false
        },
        {
          name: 'John Smith',
          email: 'jsmith@gmail.com',
          contacted: false
        },
        {
          name: 'Katty Arevalo',
          email: 'karevalo@gmail.com',
          contacted: false
        },
      ]
      
    }
  },
  methods: {
    addUser: function(e) {
      this.users.push({
          name: this.newUser.name,
          email: this.newUser.email,
          contacted: false
      });
      this.newUser.name = '';
      this.newUser.email = '';
      console.log('adding user...');
      e.preventDefault();
    }
  }
}
</script>

