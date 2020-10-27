<template>
  <div id="app">
    <div id="nav" class="logout">
      <router-link class="out"
        v-if="authenticated"
        to="/login"
        v-on:click.native="logout()"
        replace
        >Log out</router-link
      >
    </div>
    <router-view @authenticated="setAuthenticated" />
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      authenticated: false,
      mockAccount: {
        username: "truong",
        password: "123",
      },
      mockAccountUserUser: {
        username: "ao",
        password: "123",
      },
    };
  },
  mounted() {
    if (!this.authenticated) {
      this.$router.replace({ name: "login" });
    }
  },
  methods: {
    setAuthenticated(status) {
      this.authenticated = status;
    },
    logout() {
      this.authenticated = false;
    },
  },
};
</script>

<style>
body {
  background-color: #f0f0f0;
}
h1 {
  padding: 0;
  margin-top: 0;
}
#app {
  width: 1024px;
  margin: auto;
}
.logout{
  margin: 15px 0px;
  text-align: right;
}
.logout .out{
  padding: 10px;
  background: #000;
  color: #fff;
  border-radius: 5px;
  transition: all ease 0.5s;
  text-decoration: none;
}
.logout .out:hover{
  background: rgb(77, 65, 65);
}
</style>