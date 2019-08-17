<template>
  <div>
    <!-- Sign In Form -->
    <form @submit.prevent="onSubmit">
      <h2 class="card-header">Login</h2>
      <div>
        <label for="email">Email</label>
        <input type="email" v-model="email" id="email" requried />

        <label for="pass">Password</label>
        <input type="password" v-model="pass" id="pass" requried />
      </div>

      <button type="submit">Submit</button>
    </form>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  data() {
    return {
      email: "",
      pass: ""
    };
  },

  methods: {
    ...mapActions(["signIn"]),
    onSubmit() {
      const formData = {
        email: this.email,
        password: this.pass
      };

      this.signIn(formData);
    }
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Monoton&display=swap");

body {
  background-color: #385273;
}

h2 {
  text-align: center;
  font-family: "Monoton", cursive;
  font-size: 3rem;
  text-decoration: underline;
  text-decoration-color: #d98f8f;
}
form {
  padding: 20px;
  background: #f2f0ce;
  box-shadow: 2px 2px 6px rgba(255, 255, 255, 0.7);
  max-width: 400px;
  display: block;
  margin: 0 auto;
  text-align: center;
  color: #385273;
  border-radius: 25px;
}
label {
  text-align: left;
  display: block;
}
input,
button {
  padding: 5px 10px;
  margin: 5px 0;
  border: 2px solid #385273;
  color: #385273;
  background-color: transparent;
  border-radius: 20px;
}
button {
  background-color: #385273;
  color: white;
}
button:hover {
  color: #385273;
  background-color: #f2f0ce;
  transform: scale(1.1);
}
</style>
