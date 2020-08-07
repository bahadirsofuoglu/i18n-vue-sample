<template>
  <div id="app">
    <div id="nav">
      <app-switch></app-switch>
      <br />
      <Form />

      <Switch />
    </div>
  </div>
</template>
<script>
import Form from "@/components/Form.vue";
import Switch from "@/components/Switch.vue";
export default {
  components: {
    Form,
    "app-switch": Switch,
  },
};
</script>
<style></style>
