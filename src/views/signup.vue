<template>
  <div>
    <!-- Sign Up Form -->
    <form @submit.prevent="onSubmit">
      <h2 class="card-header text-center">
        Register
      </h2>

      <div>
        <label for="name">Name</label>
        <input type="text" v-model="name" id="name" requried />

        <label for="age">Age</label>
        <input type="text" v-model="age" id="age" requried />

        <label for="city">City</label>
        <input type="text" v-model="city" id="city" requried />

        <label for="job">Job Description</label>
        <input type="text" v-model="job" id="job" requried />

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
      name: "",
      age: "",
      city: "",
      job: "",
      email: "",
      pass: ""
    };
  },

  methods: {
    ...mapActions(["signUp"]),
    onSubmit() {
      const formData = {
        name: this.name,
        age: this.age,
        city: this.city,
        job: this.job,
        email: this.email,
        password: this.pass
      };
      this.signUp(formData);
    }
  }
};
</script>

<style>
form {
  padding: 20px;
  background: rgb(89, 161, 185);
  box-shadow: -2px 2px 6px;
  max-width: 500px !important;
  margin: 0 auto;
}
label {
  display: block;
}
input,
button {
  padding: 5px 10px;
  margin: 5px 0;
}
</style>
