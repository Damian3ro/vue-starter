<template>
  <div>
    <h2>Witaj {{ email }}</h2>
    <a @click="logOut()">Wyloguj</a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: ''
    }
  },
  methods: {
    enter() {
      this.$emit('login', this.email);
    }
  }
}
</script>

<style scoped>

</style>