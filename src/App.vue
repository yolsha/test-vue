<template>
  <div id="app">
    <div>
      <h1>User rating</h1>
      <Btt />
    </div>
    
    <Tabs :msg="box"/>
    
  </div>
</template>

<script>
import Tabs from "./components/Tabs";
import Btt from "./components/Btt";

export default {
  name: "App",
  data: function() {
    return {
      box: ""
    };
  },
  components: {
    Tabs, Btt
  }
};
</script>