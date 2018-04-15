<template>
  <div>
      <accountListItem
        v-for="(account, index) in accounts"
        :key="index"
        :account="account">
      </accountListItem>
  </div>
</template>

<script>
import accountListItem from './accountListItem.vue'

export default {
  props: ['accounts'],
  components: {
    accountListItem
  }
}
</script>

<style lang="scss" scoped>

</style>
