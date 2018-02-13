<template lang="html">
  <div class="idValue">
    <h1>Hello from the route of {{$route.params.id}}</h1>
  </div>
</template>

<script>
export default {
  middleware: 'search'
}
</script>

<style lang="css">
</style>
