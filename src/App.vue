<template>
  <div id="app">

    <DataTabs />

    <h1> _____________________________</h1>

    <Tabs />

  </div>
</template>

<script>
import Tabs from "./components/Tabs";
import DataTabs from "./components/DataTabs";


export default {
  name: "App",
  components: {
    Tabs, DataTabs
  }
};
</script>