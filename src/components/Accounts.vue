<template>
  <div class="accounts-container">
    <h1 class="content-header">{{ message }}</h1>
    <accountOverview v-for="account in accounts" :account="account"></accountOverview>
  </div>
</template>

<script>
import accountOverview from './accountOverview.vue'

export default {
  name: 'Accounts',
  data () {
    return {
      message: 'Accounts',
      accounts: [],
      previousTransactions: []
    }
  },
  created () {
    this.$http.get('http://localhost:3001/accounts').then(response => {
      this.accounts = response.data
    })
  },
  components: {
    accountOverview
  }
}
</script>

<style lang="scss">
  .accounts-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-areas:
        "content-header content-header"
        "account-1 account-2";
    grid-gap: 1rem;
    grid-auto-rows: minmax(50px auto);
    .content-header {
      grid-area: content-header;
      margin: 0;
      text-align: center;
    }
  }
</style>
