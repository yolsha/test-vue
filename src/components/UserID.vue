<template>
  <div 
   
  v-on:click="show =! show">

    <div>
      <img :src="user.avatar">
    </div>

    <div>

      <h1>User</h1>
      <h2> {{user.name}} </h2>

      <h2> Point </h2>
      <h3>{{user.rating}}</h3>
      
      <div v-if="show">
      <h2> Rating </h2>
      <h3>{{user.id}}</h3>
      </div>

    </div>

    <div v-if="show">
      <h2> About </h2>
      <h3>{{user.description}}</h3>
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
  },
  data: function() {
    return{
      show: false
    }
  }
}
</script>

<style>

</style>