<template>
  <v-container>
    <div v-for="user in users" :key="user.id">
      {{ user.name }}
      <v-btn x-small @click="loginUser(user)">Login</v-btn>
    </div>
  </v-container>
</template>

<script>
import { mapState } from "vuex";

export default {
  name: "Xproves",
  computed: {
    ...mapState(["users"])
  },
  mounted() {
    this.$store.dispatch("loadUsers");
  },
  methods: {
    loginUser(user) {
      this.$store.dispatch("loginUser", user);
    }
  }
};
</script>
