<template>
  <div>
    <div>
      <img :src="user.avatar">
    </div>
    <div>
      <h1>User {{user.numbe}}</h1>
      <h2> {{user.name}} </h2>
    </div>
    <div>
      <h3>{{user.point}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserID",
  props: {
    user: {
      type: Object,
      default: () => ({})
    }
  }
}
</script>

<style>

</style>