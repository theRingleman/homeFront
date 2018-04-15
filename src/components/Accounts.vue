<template>
  <div class="accounts-container">
    <h1>{{ message }}</h1>
    <accountsList :accounts="accounts"></accountsList>
  </div>
</template>

<script>
import accountsList from './accountsList.vue'

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
    accountsList
  }
}
</script>

<style lang="scss">
  .accounts-container {
    display: grid;
    grid-template-areas:
      "header",
      "account1",
      "account2"
  }
</style>
