<template>
  <div id="app">
    <header>
      <h1>Dual Mind</h1>
    </header>
    <main>
      <MessageForm />
    </main>
  </div>
</template>

<script>
import MessageForm from "./components/MessageForm.vue";

export default {
  name: "App",
  components: {
    MessageForm,
  },
};
</script>

<style>
/* Basic styling */
#app {
  font-family: Arial, sans-serif;
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  text-align: center;
}

header h1 {
  color: #fff;
}

main {
  margin-top: 20px;
}
</style>
