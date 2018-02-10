<template>
  <div >
    <h1>Search iTunes</h1><br>
    <form @submit.prevent="submitForm">
      <input type="text"
      placeholder="Enter artist name"
      v-model="search"
      autofocus>

    </form>

  </div>
</template>

<script>
export default {
  components: {

  },
  data () {
    return {
      search: ''
    }
  },
  methods: {
    submitForm() {
      this.$router.push('results')
    }
  }
}
</script>

<style>
  *{
    text-align: center;
  }
  h1{
    padding:20px;
  }
</style>
