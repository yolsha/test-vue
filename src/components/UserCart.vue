<template>
  <div>
    <div>
      <img :src="user.avatar">
    </div>
    <div>
      <h1>User</h1>
      <h2> {{user.name}} </h2>
      <h2> Point </h2>
      <h3>{{user.point}}</h3>
      <h2> Rating </h2>
      <h3>{{user.id}}</h3>
    </div>
    <div>
      <h2> About </h2>
      <h3>{{user.about}}</h3>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserCart",
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