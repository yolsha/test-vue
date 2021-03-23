<template>
  <div>

    <div>
      <UserCart />
    </div>

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
    <div>
      <h2> About </h2>
      <h3>{{user.about}}</h3>
    </div>
  </div>
</template>

<script>
import UserCart from "./UserCart";

export default {
  name: "UserID",
  props: {
    user: {
      type: Object,
      default: () => ({})
    }
  },
  components: {
    UserCart
  }
}
</script>

<style>

</style>