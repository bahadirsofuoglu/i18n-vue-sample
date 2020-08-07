<template>
  <div id="app">
    <div id="nav">
      <app-switch></app-switch>
      <br />
      <HelloWorld />

      <Switch />
    </div>
  </div>
</template>
<script>
import HelloWorld from "@/components/HelloWorld.vue";
import Switch from "@/components/Switch.vue";
export default {
  components: {
    HelloWorld,
    "app-switch": Switch,
  },
};
</script>
<style></style>
