<template>
  <div class="container">
    <div v-for="a in accounts" :key="a">
      {{ a }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  data() {
    return {
      isLoading: false,
      accounts: [],
    };
  },
  mounted() {
    this.fetchAccounts();
  },
  methods: {
    async fetchAccounts() {
      this.accounts = await this.$store.state.web3.eth.requestAccounts();
    },
  },
};
</script>
