<template>
  <div>
      <h1>User</h1>
      <h2> {{name}} </h2>
  </div>
</template>

<script>
export default {
  name: "UserID",
  props: {
    msg: String
  },
  data: function() {
    return {
      name: "asdasd"
    }
  }
}
</script>

<style>

</style>