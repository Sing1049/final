<template>
  <div class="home">
    <div
      style="display:block; width:60%; padding:30px; margin:auto; background-color:#F2F0CE;border-radius:20px;font-size:2rem;
      "
    >
      <h1 style="font-size:2rem; color:#385273;">
        Welcome to Distribution Home Page
      </h1>
    </div>

    <div class="container">
      <p class="card-text" style="color:#F2F0CE;padding:10px;">
        Are you already a Member. If <b><u>Yes</u></b> then Login or Sign in to
        Register.
      </p>
    </div>
  </div>
</template>

<script>
import { mapState, mapActions, mapGetters } from "vuex";

export default {
  computed: {
    ...mapGetters({
      auth: "isauthenticated"
    })
  }
};
</script>

<style scoped>
.home {
  text-align: center;
}
</style>
