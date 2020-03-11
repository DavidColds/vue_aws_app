<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import { AmplifyEventBus } from "aws-amplify-vue";
export default {
  mounted() {
    AmplifyEventBus.$on("authState", info => {
      console.log("auth", info);
      if (info === "signedIn") {
        this.$router.push("about");
      }
    });
  },
  name: "home",
  components: {}
};
</script>
