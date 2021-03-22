<template>
  <div id="app">
    <h1>Greetings App</h1>
    <input v-model="box" placeholder="Type your name here">
    <Tabs :msg="box"/>
    <Btt :msg="box"/>
    <UserID />
  </div>
</template>

<script>
import Tabs from "./components/Tabs";
import Btt from "./components/Btt";
import UserID from "./components/UserID";

export default {
  name: "App",
  data: function() {
    return {
      box: ""
    };
  },
  components: {
    Tabs, Btt, UserID
  }
};
</script>