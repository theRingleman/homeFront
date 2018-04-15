<template>
  <div class="account">
    <h2>{{ account.type }}</h2>
    <p><small>Created On: {{ account.created_at }}</small></p>
    <p>Current Balance: {{ account.amount }}</p>
  </div>
</template>

<script>
export default {
  props: ['account'],
  data () {
    return {
      previousTransactions: []
    }
  },
  created () {
    this.$http.get('http://localhost:3001/accounts/' + this.account.id + '/previousTransactions').then(response => {
      this.previousTransactions = response.data
      console.log(response.data)
    })
  }
}
</script>

<style lang="scss" scoped>
.account {
  margin: 25px;
}
</style>
