<template>
  <div id="app">
    <header>
      <h1>Welcome Home</h1>
    </header>
    <sidebar></sidebar>
    <main>
      <router-view/>
    </main>
    <footer></footer>
  </div>
</template>

<script>
import sidebar from './components/sidebar.vue'
export default {
  name: 'App',
  components: {
    sidebar
  }
}
</script>

<style lang="scss">
$main-brown: #554640;
$cream: #f9f5f5;

#app {
  font-family: 'Open Sans', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $cream;
  display: grid;
  grid-template-columns: 90px 1fr;
  grid-auto-rows: minmax(100px, auto);
  grid-gap: 1em;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
}

header {
  grid-area: header;
  text-align: center;
  background: $main-brown;
}

main {
  grid-area: content;
  background: $main-brown;
}

footer {
  grid-area: footer;
  background: $main-brown;
}

</style>
