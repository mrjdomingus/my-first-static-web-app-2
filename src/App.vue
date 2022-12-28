<template>
  <div>
    <div>{{ message }}</div>
    <a href="/login">Log in</a>
    <a href="/logout">Log out</a>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: ""
    };
  },
  async mounted() {
    const { body } = await (await fetch("/api/message")).json();
    this.message = body;
  }
};
</script>