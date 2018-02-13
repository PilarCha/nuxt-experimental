<template>
  <div>
    <h1>Search iTunes</h1><br>
    <v-form @submit.prevent="submitForm">
      <v-text-field
        label="Search By Name"
        v-model="search"
        required
      ></v-text-field>
    </v-form>
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
      this.$router.push(`results/${this.search}`)
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
